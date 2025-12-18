---
title: AI Projects and Experience
category: ai-projects
priority: 3
downloadable: false
---

# AI Projects and Experience

## Current AI Projects

### Project 1: Personal AI Chatbot (Resume Conversation Agent)
**Status:** Active Development  
**Platform:** Google AI Studio  
**Technology Stack:** Gemini API, RAG (Retrieval-Augmented Generation)

**Description:**  
Building a self-developed AI chatbot that enables natural conversation about professional experience and resume with high accuracy and reliability. The system leverages Google's Gemini API combined with a RAG retrieval system to access structured career data and provide contextually relevant responses about skills, projects, and experience.

**Technical Architecture:**
- **Frontend:** Custom chat interface
- **Backend:** Google AI Studio / Gemini API
- **Data Layer:** Structured knowledge base with RAG retrieval
- **Accuracy Mechanism:** Retrieval-augmented generation ensures responses are grounded in actual documented experience

**Purpose:**  
Enable website visitors to have interactive conversations about career history, skills, and experience without manufacturing or hallucinating information. The RAG system ensures every response is traceable to source documentation.

**Key Challenges Solved:**
- Maintaining factual accuracy through RAG architecture
- Structuring career data for optimal retrieval
- Balancing conversational fluency with precision
- Preventing AI hallucination about experience

---

### Project 2: Multi-Agent Resume Generator (Open Source)
**Status:** Active Development  
**Platform:** GitHub (Open Source)  
**Architecture:** Multi-agent agentic workflow

**Description:**  
An open-source automated resume generation system using a multi-agent workflow that matches job descriptions to relevant experience, writes tailored resumes, and performs accuracy validation. Built after extensive research of resume best practices and advice across multiple sources.

**Agent Architecture:**

**Agent 1: Keyword Extraction & Matching**
- Parses job descriptions to extract key requirements, skills, and keywords
- Matches keywords to relevant work experience in structured database
- Ranks and prioritizes most relevant experiences
- Serves matched content to writing agent

**Agent 2: Resume Writer**
- Receives matched experience from Agent 1
- Writes resume content based on predefined template
- Template developed from extensive research of resume advice, blogs, and best practices
- Maintains consistent voice and formatting
- Optimizes for ATS (Applicant Tracking Systems) compatibility

**Agent 3: Fact-Checker & Reviewer**
- Performs final validation of generated content
- Flags inaccurate or false statements
- Identifies gaps between job description keywords and actual experience coverage
- Provides coverage analysis showing alignment between JD requirements and resume content
- Returns flagged items for human review or Agent 2 revision

**Technical Foundation:**
- Structured career database (source of truth)
- Template system based on resume research
- Multi-pass validation workflow
- Gap analysis and coverage reporting

**Philosophy:**  
Never manufacture experience. The system can only write about what exists in the structured database. The fact-checker ensures accuracy and flags any hallucinations or gaps, requiring human judgment for final decisions.

**Open Source Goals:**
- Democratize access to intelligent resume tailoring
- Share learnings from resume research and template development
- Build community around ethical AI-assisted job applications
- Provide transparency into the agentic workflow

---

## AI Implementation at Veranex Solutions

### Role: Sr Director of Marketing, UXBrand and Creative

**AI Integration Scope:**  
Led comprehensive AI adoption across marketing operations, from copywriting and creative generation to automated multi-asset workflows and agentic creative development systems.

### Use Case 1: AI-Powered Copywriting
**Implementation:** Integrated LLMs for marketing copy generation across email campaigns, landing pages, blog content, and ad copy
**Maturity Level:** Production use with human review
**Results:** Accelerated content production velocity while maintaining brand voice consistency
**Key Learnings:** AI excels at first drafts and variations; human editing remains essential for strategic messaging and brand alignment

### Use Case 2: Creative Asset Generation
**Implementation:** Used AI for image generation, creative concept exploration, and visual asset development
**Tools:** Merlin AI and other generative image platforms
**Workflow:** Rudimentary but functional automated workflows for creative generation
**Results:** Expanded creative exploration capacity, enabling more concept testing before committing design resources

### Use Case 3: Multi-Format Asset Regeneration
**Problem Statement:** Single creative assets needed adaptation across multiple formats, channels, and dimensions
**Solution:** Built automated workflows to take one master asset and regenerate into multiple formats
**Technical Implementation:** AI-powered reformatting, resizing, and content adaptation
**Business Impact:** Dramatically reduced manual production time for multi-channel campaigns
**Example Use Cases:**
- Social media format variations (square, vertical, horizontal)
- Email vs. landing page vs. display ad adaptations
- Mobile vs. desktop optimizations

### Use Case 4: Agentic Creative Workflow (Advanced)
**Status:** In development/early implementation  
**Architecture:** Multi-stage agentic system for creative concept development

**Workflow Stages:**

**Stage 1: Idea Input**
- Marketing team inputs creative briefs, campaign goals, and initial concepts into structured folders
- Briefs include boundaries, brand guidelines, target audience, and success criteria

**Stage 2: AI Concept Development**
- Agentic workflow processes inputs within defined boundaries and guidelines
- Generates multiple creative concepts, copy variations, and visual directions
- Operates within brand guardrails and strategic constraints
- Returns concepts for human review and approval

**Stage 3: Human Review & Approval**
- Marketing team reviews AI-generated concepts
- Provides feedback, selects directions, or requests iterations
- Maintains strategic oversight and brand integrity
- Approves concepts for production

**Stage 4: Creative Production**
- Once approved, AI generates final creative assets
- Produces multi-format variations automatically
- Maintains consistency with approved concept
- Delivers production-ready files

**Philosophy:**  
AI accelerates exploration and production, but humans maintain creative direction and strategic decision-making. The system amplifies team capacity without replacing judgment.

**Key Success Factors:**
- Clear boundaries and brand guidelines
- Structured input requirements
- Human-in-the-loop approval gates
- Iterative refinement capability

---

## AI Tools & Daily Workflow

### Coding & Development
**Tool:** GitHub Copilot  
**Integration:** VS Code  
**Use Cases:**
- Frontend development (CSS/SCSS/Tailwind - 4/5 proficiency)
- React/Vue component building (3/5 proficiency)
- Architecting layouts and fixing complex styling bugs
- Rapid prototyping of interactions
- Code documentation and optimization

**Impact:** Significantly accelerated development velocity, particularly for prototyping and production bug fixes

### Research & Analysis
**Primary Tool:** Perplexity  
**Use Cases:**
- Competitive analysis and market research
- Product hypothesis validation
- Technical documentation research
- Healthcare/MedTech industry insights
- Cited, sourced information for decision-making

**Why Perplexity:** Provides sourced, cited responses that save hours of cross-referencing. Critical for evidence-based decision-making in high-stakes environments.

### LLM Rotation Strategy
**Tools:** ChatGPT, Claude (Anthropic), Google Gemini  
**Approach:** Task-specific LLM selection based on strengths
- **ChatGPT:** General problem-solving, brainstorming, coding assistance
- **Claude:** Long-form content, nuanced analysis, ethical reasoning
- **Gemini:** Integrated workflows, structured data processing

**Local LLMs:** Ollama (Meta Llama 3) for privacy-sensitive tasks and experimentation

### Creative AI
**Tool:** Merlin AI  
**Purpose:** Image generation and model aggregation  
**Use Cases:** Creative concept exploration, asset generation, visual prototyping

---

## AI Philosophy & Approach

### Core Principles

**1. AI as Amplification, Not Replacement**
AI should multiply human capability and free up time for high-value work. Strategic decisions—understanding user needs, balancing business constraints, making ethical choices—remain firmly in human hands.

**2. Accuracy Through Architecture**
Use RAG, fact-checking agents, and structured data to prevent hallucination. Never allow AI to manufacture experience or information. Build systems that enforce accuracy by design.

**3. Designers Must Lead AI Integration**
Designers understand user needs at the deepest level. We must lead AI integration to ensure technology serves users' actual needs rather than just engagement metrics or efficiency for its own sake.

**4. Transparency in AI Systems**
Open-source sharing, clear documentation of AI involvement, and honest communication about capabilities and limitations. Users deserve to know when and how AI is being used.

**5. Human-in-the-Loop for High-Stakes Decisions**
In healthcare, enterprise software, and career decisions, AI should inform but not replace human judgment. Build approval gates and review processes into automated workflows.

### AI in Product Design Strategy

**Adaptive UI Vision:**  
Exploring interfaces that use AI to identify and reduce friction points automatically, creating deeply personalized user experiences. In MedTech, where physical context matters enormously (cardiac arrest in the field vs. therapist with 5 minutes in an office), AI could help software adapt to environment and user stress level in real-time.

**AI-Powered Personalization:**  
Integrate AI thoughtfully into both workflows and products to enhance beneficial experiences—not just hold user attention with generic outputs. Focus on genuine value creation over engagement metrics.

**Design Systems + AI:**  
Potential to use AI for:
- Analyzing usage patterns across teams
- Suggesting component optimizations
- Flagging accessibility issues before shipping
- Generating documentation automatically
- Handling repetitive governance tasks

Could potentially double the 50% velocity improvement already achieved with traditional design systems.

---

## Business Impact of AI Integration

### Veranex Website Redesign (1400% Conversion Improvement)
**AI Contribution:**  
While the conversion improvement came from strategic UX decisions, AI tools accelerated the research and iteration phases:
- Used Perplexity and ChatGPT to analyze competitor sites rapidly
- Synthesized 30+ user interviews faster with AI assistance
- Prototyped multiple approaches quickly using AI-assisted coding
- Tested more hypotheses through three release cycles with accelerated development

**Result:** Speed enabled more iteration, leading to better outcomes. AI amplified research and development capacity.

### Marketing Automation & Enrichment
**Tools:** Clearbit, Breeze Intelligence (AI-powered form enrichment)  
**Strategy:** Use AI enrichment to reduce form fields while capturing complete data  
**Impact:** Directly contributed to conversion rate optimization. Removing friction intelligently through AI-powered enrichment makes high conversion possible at scale.

### Team Leadership & AI
**Current Exploration:**  
Investigating how AI can help leaders process information faster, identify patterns in team performance, and free up time for high-value human work (empathy, mentorship, strategic planning).

**Constraint:** AI cannot replace the human elements of leadership—empathy, planned reactions, ability to inspire toward shared goals. Exploring how to scale mentorship without losing personal connection.

---

## Future Speaking Topics

### AI in MedTech
**Focus Areas:**
- Adaptive UI for high-stakes healthcare environments
- AI-powered personalization in medical device software
- Balancing AI capabilities with regulatory requirements (FDA, EU MDR)
- Privacy and security in AI-enabled healthcare products

### AI in Enterprise Software
**Focus Areas:**
- AI-enhanced workflows for productivity software
- Adaptive interfaces that learn user patterns
- Friction reduction through intelligent automation
- Designing for AI transparency and user trust

---

## Technical AI Skills

**Current Proficiency:**
- AI API integration (Gemini, OpenAI, Anthropic) - Intermediate
- RAG architecture design and implementation - Learning/Intermediate
- Multi-agent workflow orchestration - Active development
- Prompt engineering for production systems - Proficient
- LLM evaluation and selection - Proficient
- Local LLM deployment (Ollama) - Beginner/Intermediate

**Not an ML Engineer:**  
Strength is bridging the gap between what's technically possible and what actually serves users—translating AI capabilities into meaningful product features that improve workers' lives.

---

## Open Source AI Contributions

### In Development
**Multi-Agent Resume Generator**  
Status: Active development, planned open source release  
Purpose: Democratize access to intelligent resume tailoring while maintaining ethical standards and factual accuracy

### Future Projects
Exploring opportunities to create open-source resources that help designers work more effectively with AI, similar to approach with UXTOOLTIME-Axure (86 GitHub stars). Focus on democratizing design tools and sharing learnings with community.

---

## AI Learning & Development

**Current Focus:**
- AI-driven product development methodologies
- Local LLM implementation and optimization
- Adaptive interface architecture at scale
- AI integration in healthcare software with regulatory compliance
- Agentic workflow design patterns
- RAG system optimization for accuracy

**Research Interests:**
- AI in Design Systems and Scalable Operations
- Ethical AI in high-stakes environments
- AI-enhanced user research methods
- Privacy-preserving AI architectures
- AI transparency and explainability in product design

---

## Key Differentiators in AI Space

1. **Healthcare + AI Expertise:** Unique combination of MedTech domain knowledge and AI implementation experience in regulated environments

2. **Production AI Experience:** Not theoretical—shipped AI-powered marketing systems generating real business results at enterprise scale

3. **Multi-Agent Architecture:** Hands-on development of agentic workflows with fact-checking and accuracy validation

4. **RAG Implementation:** Building accuracy-first AI systems that prevent hallucination through architecture

5. **Open Source Philosophy:** Committed to sharing learnings and democratizing AI tools for designers and job seekers

6. **AI + Design Systems Authority:** Exploring intersection of two high-impact areas for multiplicative velocity improvements

---

## Questions for Knowledge Base Retrieval

**Q: What AI tools does Gary use in his daily workflow?**  
A: GitHub Copilot integrated into VS Code for coding, Perplexity as primary research engine, and rotation between ChatGPT, Claude (Anthropic), and Google Gemini depending on task. Also runs local LLMs via Ollama (Meta Llama 3) and uses Merlin AI for image generation and model aggregation.

**Q: What AI projects is Gary currently building?**  
A: Two main projects: (1) A personal AI chatbot using Google's Gemini API with RAG retrieval for accurate conversations about his resume and experience, and (2) an open-source multi-agent resume generator that matches job descriptions to experience, writes tailored resumes, and performs fact-checking validation.

**Q: How does Gary's multi-agent resume system work?**  
A: Three-agent workflow: Agent 1 extracts keywords from job descriptions and matches to structured experience database. Agent 2 writes resume based on research-backed template. Agent 3 fact-checks output, flags inaccuracies, and identifies gaps between job requirements and actual experience coverage. Never manufactures experience—only uses documented work history.

**Q: How did Gary use AI at Veranex Solutions?**  
A: Led AI integration across marketing operations including copywriting, creative asset generation, multi-format asset regeneration (taking one asset and creating variations), and developed agentic workflows where AI processes creative briefs within brand guidelines, returns concepts for approval, then generates final creative assets. Workflow included human approval gates to maintain strategic oversight.

**Q: What's Gary's philosophy on AI in design?**  
A: AI should amplify human capability, not replace human judgment. Designers must lead AI integration to ensure it serves users' actual needs rather than just engagement metrics. Use architecture (like RAG) to enforce accuracy. Maintain human-in-the-loop for high-stakes decisions. Focus on transparency and ethical implementation.

**Q: What's Gary's vision for AI in MedTech?**  
A: Particularly interested in Adaptive UI—interfaces that use AI to identify and reduce friction points automatically, creating deeply personalized experiences. In MedTech, where physical context matters (cardiac arrest in field vs. therapist in office), AI could help software adapt to environment and user stress level in real-time while maintaining regulatory compliance.

**Q: How did AI contribute to Gary's 1400% conversion improvement at Veranex?**  
A: AI tools accelerated research and iteration phases: used Perplexity and ChatGPT to analyze competitors, synthesized 30+ user interviews faster, prototyped multiple approaches quickly with AI-assisted coding. The speed enabled testing more hypotheses through three release cycles, though strategic UX decisions drove the core improvement.

**Q: What AI-powered marketing automation did Gary implement?**  
A: Used AI enrichment tools (Clearbit, Breeze Intelligence) for form field reduction while capturing complete data, directly impacting conversion rates. Built workflows for multi-format asset regeneration. Developed agentic creative workflows where AI generates concepts within brand boundaries, returns for approval, then produces final assets.

**Q: What's Gary's technical proficiency with AI?**  
A: Intermediate AI API integration (Gemini, OpenAI, Anthropic), learning RAG architecture, active development in multi-agent workflows, proficient in prompt engineering and LLM selection. Not an ML engineer—strength is bridging gap between technical possibility and user needs, translating AI capabilities into meaningful product features.

**Q: What AI skills is Gary currently developing?**  
A: Deepening AI-driven product development, exploring local LLM implementation via Ollama, studying adaptive interface architecture at scale, researching AI integration in healthcare software with regulatory compliance (FDA, EU MDR), learning RAG system optimization, and developing multi-agent workflow design patterns.

**Q: Why does Gary use Perplexity as his primary research engine?**  
A: Provides cited, sourced information that saves hours of cross-referencing. Essential for competitive analysis, market research, and validating product hypotheses with confidence. Sourced responses enable data-driven decision-making in high-stakes environments.

**Q: How does Gary's RAG-based chatbot ensure accuracy?**  
A: Uses Retrieval-Augmented Generation architecture with structured knowledge base. Every response is grounded in actual documented experience, making information traceable to source. RAG prevents AI hallucination by requiring retrieval from verified data before generating responses.

**Q: What's Gary's approach to AI in team leadership?**  
A: Exploring how AI can help leaders process information faster and identify team performance patterns, freeing time for high-value human work. However, AI cannot replace human elements of leadership—empathy, planned reactions, ability to inspire toward shared goals. Investigating how to scale mentorship without losing personal connection.

**Q: How does Gary think about AI and design systems?**  
A: Design systems could use AI to analyze usage patterns, suggest component optimizations, flag accessibility issues, generate documentation, and handle repetitive governance tasks. The 50% velocity improvement from traditional design systems could potentially double with intelligent automation.

**Q: What open-source AI projects is Gary planning?**  
A: Multi-agent resume generator (in active development) to democratize intelligent resume tailoring while maintaining ethical standards. Exploring future projects similar to UXTOOLTIME-Axure approach—creating open-source resources that help designers work effectively with AI and sharing learnings with community.

**Q: What's Gary's stance on AI accuracy and hallucination?**  
A: Build accuracy through architecture, not prompting alone. Use RAG, fact-checking agents, and structured data to prevent hallucination. Never allow AI to manufacture experience or information. In multi-agent resume system, Agent 3 specifically validates accuracy and flags any false statements.

**Q: How does Gary see designers' role in the AI era?**  
A: Designers must position as leaders in AI integration, not passengers. We understand user needs at deepest level. Our job is ensuring AI enhances human capability rather than replacing human judgment, especially in high-stakes environments like healthcare and enterprise software. Designers should lead the evolution.

**Q: What AI conference topics is Gary developing?**  
A: "AI in MedTech" focusing on adaptive UI for healthcare, AI-powered personalization in medical device software, and balancing AI with regulatory requirements. "AI in Enterprise Software" covering AI-enhanced workflows, adaptive interfaces, friction reduction through intelligent automation, and designing for AI transparency and user trust.

---

meta
  created: 2025-12-17
  category: ai-projects
  tags:
    - Artificial Intelligence
    - AI Projects
    - Multi-Agent Systems
    - RAG Architecture
    - Gemini API
    - Agentic Workflows
    - Marketing Automation
    - AI Tools
    - Open Source AI
    - Design + AI
    - MedTech AI
    - AI Ethics
  related_files:
    - technical-skills.md
    - design-philosophy.md
    - professional-summary.md
    - conference-talks.md
  priority: high
  status: active-development
