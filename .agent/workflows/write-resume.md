---
description: write a resume
---

## 1. Resume Writer
**Trigger:** User asks to run "resume workflow" 

### Phase 1: Research Agent Activation
**Trigger:** User submits job description file `/Input/Job-Description.md`
**Input provided to agent:**
- Job description file path
- KB folder path: `/Knowledge Base/`
- Brain folder output path: `/brain/research_output/`

**Wait for:** `research_complete: true` signal

**Validation checklist:**
- [ ] Brain folder contains `ats_keywords.json`
- [ ] Brain folder contains `matched_experiences.json`
- [ ] Minimum 15 ATS keywords extracted
- [ ] At least 60% keyword coverage from KB

**On success:** Proceed to Phase 2
**On failure:** Return error to user requesting additional career documentation

---

### Phase 2: Writer Agent Activation
**Trigger:** Research phase validation passed
**Input provided to agent:**
- Brain folder path: `/brain/research_output/`
- Structure folder path: `/structure/`
- KB folder path (for tone reference): `/Knowledge Base/`

**Wait for:** `draft_complete: true` signal

**Validation checklist:**
- [ ] Output files exist: `/output/resume_draft.pdf` and `/output/resume_draft.md`
- [ ] Resume follows structure template section order
- [ ] All content traceable to KB sources
- [ ] Minimum 70% ATS keyword integration

**On success:** Proceed to Phase 3
**On failure:** Return to Writer with specific gaps highlighted (max 2 loops)

---

### Phase 3: Reviewer Agent Activation
**Trigger:** Writer phase validation passed
**Input provided to agent:**
- Resume draft path: `/output/resume_draft.md`
- Original job description file path
- KB folder path: `/Knowledge Base/`
- Review output path: `/output/review_report.json`

**Wait for:** `review_complete: true` signal

**Validation checklist:**
- [ ] ATS score ≥ 75
- [ ] Fact-check status = "PASS"
- [ ] Zero fabrication flags

**On success:** Deliver final resume + review report to user
**On failure:** Return to Writer with revision instructions from review report (max 2 loops)