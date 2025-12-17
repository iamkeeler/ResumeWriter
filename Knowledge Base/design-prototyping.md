---
title: "Design, Prototyping, and Analytics"
category: "design-tools"
priority: 4
downloadable: false
---

## Design, Prototyping, and Analytics

### Prototyping Strategy & Tooling
*   **Tool Selection:** The choice of tool is dictated by the required fidelity for handoff and testing.
    *   **Figma:** The primary driver for "quick and good enough" prototyping and daily design work.
    *   **Axure:** Deployed when high-fidelity situational logic is required (e.g., complex workflows with conditional paths that Figma cannot handle).
*   **Open Source Contributions (UX ToolTime):**
    *   **Origin:** Created initially to accelerate the internal team's prototyping velocity.
    *   **Community Impact:** Released as a free resource to "give back" to the design community, garnering over 60,000 downloads before being sunset.

### Validation & Testing
*   **Standard Validation Loop:** Preference for "quick and dirty" unmoderated testing on small, discoverable workflow chunks.
    *   **Philosophy:** Unmoderated testing is favored to minimize "leading the witness" and ensure unbiased initial reactions. Moderated sessions are used but treated with caution to avoid influencing user feedback.
    *   **Validity:** Heavy emphasis on crafting test scenarios that avoid leading questions, ensuring users aren't just providing the feedback they think the designer wants.

### Analytics Instrumentation
*   **Process:** Deeply involved in defining the tracking plan from day one.
    *   **Collaboration:** Partners with data engineers (when available), PMs, and stakeholders to define *actionable metrics*—avoiding vanity metrics in favor of data points that reveal true user behavior and deviation from expected paths.
    *   **Implementation:** Builds instrumentation specifically to support these defined goals, ensuring every data point serves a strategic purpose.

### A/B Testing & Experimentation
*   **Case Study (Sage Therapeutics):**
    *   **Scenario:** A mental health application where the design team preferred a version with superior aesthetics and color theory.
    *   **Result:** A secondary, "inferior" looking design won significantly due to better action placement.
    *   **Team Management:** When the team was surprised/skeptical, they were encouraged to build out the winning version fully and re-run the test. The second test confirmed the results, revealing a missed user requirement regarding a key action. This turned a "loss" for the design team into a validated learning moment about user needs over aesthetics.

### Design Systems & Governance
*   **Pragmatic Implementation:** To avoid the trap of "shelfware" design systems, the focus is on mirroring the development environment.
    *   **Workflow:** For the Veranex website (WordPress/HubSpot), Figma components and tokens were built to exactly mirror the live CMS components.
    *   **Speed:** This allowed for rapid prototyping in Figma that could be uploaded to Miro for feedback, ensuring that what was approved in design could be immediately and accurately built by developers.
