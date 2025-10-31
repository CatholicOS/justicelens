# JusticeLens — AI Legal Triage Assistant

**JusticeLens** is an AI-powered post-conviction triage assistant that helps identify potential sentencing and conviction errors, summarizes them in plain English for families, and creates structured memos for attorneys or legal clinics.

It is **educational only** and **not legal advice**.

---

## Overview

JusticeLens analyzes uploaded case materials to flag **common, high-impact, and often-overturned errors** such as:

- Habitual-offender or three-strikes misapplications  
- Guideline or range miscalculations  
- Concurrency and time-credit issues  
- Plea colloquy defects  
- Apprendi / Blakely / Alleyne violations  
- Brady / Giglio / Ineffective assistance patterns  

### Two synchronized outputs

| View | Description |
|------|--------------|
| **Family View** | Plain-language summary (English + Spanish): what seems wrong, why it matters, and what to do next |
| **Lawyer View** | Structured memo with issue matrix, record cites, legal authority, and next steps |

---

## ⚙️ Key Components

| File | Purpose |
|------|----------|
| `JusticeLens_Instructions.md` | Core operating instructions for the GPT |
| `JusticeLens_Knowledge.md` | Reference playbook: schema, scoring, templates |
| `JusticeLens_PrivacyPolicy.md` | Data and privacy statement |
| `JusticeLens_FreeActions_withGuidance_OAS3.1.json` | Free public legal-data API (CourtListener / Free Law Project) |
| `JusticeLens_Demo_*` files | Fictional Georgia case package for demo/testing |

> **Note:** Future versions plan to integrate [GraphRAG](https://github.com/microsoft/graphrag) for cross-document knowledge-graph reasoning, but it is **not part of the MVP**.

---

## Quick Start (for local review or contributors)

1. Clone this repository.  
   ```bash
   git clone https://github.com/YOUR_USERNAME/JusticeLens.git
   cd JusticeLens
   ```

2. Review the documentation files in order:
   - `JusticeLens_Instructions.md` — defines how the GPT interprets cases.  
   - `JusticeLens_Knowledge.md` — contains structured templates and scoring.  
   - `JusticeLens_PrivacyPolicy.md` — outlines privacy and data-handling policies.

3. In ChatGPT’s **Custom GPT Builder**:
   - Upload the above files into the **Knowledge** and **Instructions** sections.  
   - Add the API spec `JusticeLens_FreeActions_withGuidance_OAS3.1.json` under **Actions** to enable CourtListener / Free Law Project lookups.  
   - Upload the demo files to test outputs.

4. Test with conversation starters such as:
   - “Review my case — ask me what you need to start the analysis.”  
   - “Revisa mi caso — pregúntame qué necesitas para comenzar el análisis.”  

---

## Privacy & Ethics

- JusticeLens does **not store private data** outside of the ChatGPT environment.  
- It uses **public legal data** only (CourtListener, govinfo, etc.).  
- Users are encouraged to **redact personal identifiers** before uploading files.  
- Every output includes clear disclaimers and guidance to consult counsel or a legal clinic.

See [`JusticeLens_PrivacyPolicy.md`](./2025-10-23%20JusticeLens_PrivacyPolicy.md) for full details.

---

## Project Structure

```
.
├── README.md
├── JusticeLens_Instructions.md
├── JusticeLens_Knowledge.md
├── JusticeLens_PrivacyPolicy.md
├── JusticeLens_FreeActions_withGuidance_OAS3.1.json
├── JusticeLens_Demo_CaseData.json
├── JusticeLens_Demo_IssueMatrix.csv
├── JusticeLens_Demo_Report.md
└── assets/
    └── JusticeLens_Logo.png
```

---

## Contributing

We welcome contributions that improve accuracy, accessibility, or expand jurisdictional coverage.

1. Fork this repository.  
2. Create a new branch (`git checkout -b feature/your-feature`).  
3. Commit changes and open a pull request.  

Potential areas for contribution:
- Additional state-specific sentencing templates  
- Expanded legal-aid routing lists  
- Enhanced CSV/JSON export automation  

---

## Contact

**Maintainer:** Michael Lyons  
**Email:** michael.lyons@yimpactventures.com  
**Purpose:** Educational AI assistant for sentence review and legal research.  

---

## 🪧 Disclaimer

JusticeLens is **not a law firm** and does **not provide legal advice**.  
All outputs are educational and must be verified with a qualified attorney or legal clinic.
