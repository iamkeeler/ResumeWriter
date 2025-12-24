---
title: Brick Run - Wear OS Roguelike Brick Breaker
category: Mobile Game Development
priority: 3
downloadable: false
---

# Brick Run – Wear OS Roguelike Brick Breaker

A roguelike brick-breaker game built exclusively for Wear OS devices with procedural level generation, run-based progression, and a rich upgrade system. The project showcases modern Android development practices tailored for wearable devices with both round and square displays.

---

## Project Overview

**Name:** Brick Run (formerly Brick Rogue)  
**Platform:** Wear OS (Android 28+, Wear OS 4+)  
**Status:** Active Development  
**License:** MIT

### Core Features

- **Roguelike Progression** – Run-based gameplay with permanent meta-progression and temporary per-run upgrades
- **Procedural Levels** – Algorithm-generated brick patterns with scaling difficulty
- **8 Unlockable Ball Types** – Each with unique modifiers, visual styles, and gameplay mechanics
- **20+ Upgrade Types** – Categorized by rarity with synergy effects
- **Dual Input Methods** – Touch gestures and rotary crown support
- **60fps Gameplay** – Fixed-timestep game loop with object pooling for battery efficiency
- **Circular Timer** – Visual countdown using the watch bezel instead of numerical display

---

## Architecture

### Multi-Module Clean Architecture

```
app/           → Presentation layer (Compose UI, ViewModels, Activities)
domain/        → Pure Kotlin business logic (no Android dependencies)
data/          → Data persistence + repository implementations
game-engine/   → Testable game loop & physics (60fps fixed-timestep)
```

### Tech Stack

| Layer | Technology |
|-------|------------|
| **UI** | Jetpack Compose for Wear OS + Material 3 Expressive |
| **Architecture** | MVVM + Clean Architecture with Repository pattern |
| **DI** | Manual dependency injection via ViewModelFactory |
| **Persistence** | DataStore for preferences, Room for high scores |
| **Build** | Kotlin 2.0.21, AGP 8.9.0, Gradle Kotlin DSL |
| **Testing** | JUnit, Turbine (Flow testing), MockK |

### Key Design Patterns

1. **GameEngine State Coordination** – Engine manages physics via fixed-timestep loop, exposes `StateFlow<GameState>` and `SharedFlow<GameEvent>` for UI observation
2. **Overlay-Driven UI** – Game state transitions use overlay composables (Pause, Score, GameOver, LevelComplete) instead of separate screens
3. **Modifier System** – `ModifierCatalog` defines upgrade specs → `ModifierCalculator` resolves stacks → `ModifierState` applies to entities
4. **Object Pooling** – Lazy-initialized pools for balls, bricks, and particles to minimize allocations during gameplay

---

## Game Mechanics

### Core Game Loop

1. **Level Start** → Player launches ball with current upgrades
2. **Active Play** → Ball bounces, destroys bricks, builds combos
3. **Level Clear** → Time bonus + currency calculation
4. **Upgrade Shop** → Spend currency on temporary/permanent upgrades
5. **Next Level** → Increased difficulty, new brick patterns
6. **Endless Mode** → After level 9, optional infinite progression

### Ball Types & Unlock Progression

| Ball | Unlock | Key Modifiers |
|------|--------|---------------|
| **Classic** | Start | Baseline gameplay, 60s timer |
| **Speedster** | After Classic | +20% ball speed |
| **Powerhouse** | After Speedster | +30% damage, -20% speed, -10% paddle |
| **Lucky** | After Powerhouse | 2.5x special brick spawn |
| **Mini** | After Lucky | -20% ball/paddle size, +55% score |
| **Miser** | After Mini | Reduced coins/interest, +100% score |
| **Explosive** | After Miser | 4x bomb spawn, guaranteed 1 bomb/level, -25% score |
| **Swarm** | After Explosive | Start with 3 balls, +100% hardened bricks, -50% damage |

### Upgrade System

**Rarity Tiers:** Common → Uncommon → Rare → S-Tier

**Categories:**
- **Paddle:** Size, Stability, Magnetic
- **Ball:** Speed, Damage, Multi-ball, Chain Reaction
- **Economy:** Interest, Coin Value, Time Bonus
- **Offensive:** Bomb Factory, Bomb Damage, Weaken Bricks

### Currency & Economy

- **Base Level Reward:** $5/level (configurable per ball type)
- **Coin Bricks:** 1-3 coins per brick
- **Interest:** 10% on (previous balance + coin bricks), capped at $10
- **Time Bonus:** Bonus for fast completions
- **Reroll System:** Refresh shop offers with increasing cost

---

## UI/UX Design

### Wear OS Optimization

- **Round vs Square Detection** – `Configuration.isScreenRound` triggers adaptive layouts
- **Circular Timer** – Progress arc around bezel edges, color-coded (green → orange → red)
- **Crown Scrolling** – TransformingLazyColumn for crown-scrollable lists
- **Edge Buttons** – M3E EdgeButton for primary actions at screen bottom
- **Adaptive Padding** – Different spacing tokens for round (24dp corners) vs square (16dp) displays

### Material 3 Expressive Components

```kotlin
// Pattern: M3E TransformingLazyColumn with crown scrolling
TransformingLazyColumn(
    state = rememberTransformingLazyListState(),
    contentPadding = PaddingValues(...)
) {
    items(upgrades) { UpgradeCard(it) }
}
```

### Input Methods

| Input | Usage |
|-------|-------|
| **Horizontal Drag** | Primary paddle control |
| **Rotary Crown** | Precise paddle adjustment (0.15f sensitivity) |
| **Single Tap** | Pause/Resume, confirm selections |
| **Long Press** | Shop access between levels |

---

## Development Workflow

### Build Commands

```bash
# Build debug APK
./gradlew assembleDebug

# Install to connected Wear device
./gradlew installDebug

# Run unit tests
./gradlew test

# Run specific module tests
./gradlew :domain:test
./gradlew :game-engine:test
```

### Key Source Files

| File | Purpose |
|------|---------|
| `GameEngine.kt` | 800+ lines core game loop with coroutines |
| `GameState.kt` | Single source of truth for all game state |
| `ModifierCatalog.kt` | 30KB+ upgrade system definitions |
| `BallType.kt` | 8 ball types with visual & modifier configs |
| `GameOverlays.kt` | 1400+ lines overlay composables |
| `MainActivity.kt` | Navigation hub with SwipeDismissableNavHost |
| `GameActivity.kt` | Standalone game session |

### Testing Infrastructure

- **Unit Tests:** ModifierCatalog, business logic, ViewModels with Turbine
- **Android Tests:** Compose UI tests for Settings, Shop, Developer Options
- **Benchmarks:** Performance tests for game loop frame times

---

## Performance Optimization

### 60fps Target

- **Fixed Timestep:** 16.67ms per frame
- **Object Pooling:** `ObjectPool<T>` for balls, bricks, particles
- **Particle Limit:** 4-8 per brick destruction
- **Lazy Loading:** Upgrade shop content loaded on demand

### Battery Efficiency

- **Wake Lock Management:** Active only during gameplay, released on pause/shop
- **State Persistence:** 3-tier autosave (level start, level complete, lifecycle events)
- **Minimal Allocations:** No allocations in game loop hot path

---

## Notable Implementation Details

### Seed System

5-character alphanumeric seeds (base-36 encoding) for reproducible level generation. Example: `1732406789123L` → `"21I7P"`

### Chain Reaction System

Per-ball hit counters for upgrade-triggered chain reactions, with visual spark effects that scale per ball.

### Softlock Prevention

Magnetic pull system activates after 10 consecutive wall bounces without paddle/brick contact, gradually pulling ball toward paddle center.

### Progress Persistence

3-tier protection:
1. Priority 1: Save on `startNextLevel()` 
2. Priority 2: Save on `GameEvent.LevelComplete`
3. Priority 3: Lifecycle-based autosave on Activity pause/stop

---

## Documentation Index

- **[copilot-instructions.md](.github/copilot-instructions.md)** – Technical implementation guide
- **[game-mechanics.md](.github/game-mechanics.md)** – Gameplay systems and balance
- **[ui-ux.md](.github/ui-ux.md)** – Interface patterns and visual design
- **[to-do-list.md](to-do-list.md)** – Feature backlog and completed items

### Implementation Plans (docs/)

- Ball mechanics, chain reactions, explosives
- Shop UI, upgrade verification
- Endless mode, animation bugs
- Play Store release guide

---

## Future Roadmap

- Additional Ball Types
- Online Leaderboard
- More Upgrades
- Gyroscope Controls
- Apple Watch (watchOS) Port

---

## Summary

Brick Run demonstrates a complete, production-quality Wear OS game with:

- **Modern Android Architecture:** Multi-module Clean Architecture with MVVM
- **Wearable-First Design:** Round/square adaptive UI, crown input, battery optimization  
- **Deep Gameplay Systems:** 8 ball types, 20+ upgrades, roguelike progression
- **Performance Focus:** 60fps fixed-timestep loop with object pooling
- **Comprehensive Documentation:** 98+ markdown files covering all systems

The codebase serves as a reference implementation for building performant, visually polished games on Wear OS using Jetpack Compose and Material 3 Expressive design patterns.
