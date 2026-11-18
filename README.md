# Awesome-Legal-Clause-Library-Standard-Clauses
# Awesome-Legal-Clause-Library-Standard-Clauses

# Awesome Legal Clause Library & Standard Clauses

> A curated list of top Legal Clause Library and Standard Clause platforms — both SaaS/Hosted commercial CLM suites and open-source alternatives for centralizing approved clause language, fallback positions, and playbook-driven drafting.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Icertis Clause Library](#icertis-clause-library)
  - [Ironclad Clause Library](#ironclad-clause-library)
  - [DocuSign CLM Clause Library](#docusign-clm-clause-library)
  - [Conga Clause Library](#conga-clause-library)
  - [Agiloft Clause Library](#agiloft-clause-library)
  - [CobbleStone Clause Management](#cobblestone-clause-management)
  - [Robin AI Clause Library](#robin-ai-clause-library)
- [Open-Source Software](#-open-source-software)
  - [template-vault](#template-vault)
  - [draftLegal](#draftlegal)
  - [Codify Core](#codify-core)
  - [OpenCLM](#openclm)
  - [contract-vault](#contract-vault)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Legal Clause Library and Standard Clause platforms. These are not open-source but are included as reference points for feature comparison.

### Icertis Clause Library
**Type:** Clause library with AI-generated playbooks
Icertis provides clause-level intelligence within its contract lifecycle management platform, with an AI-first experience layer that lets teams draft, review, and understand agreements through conversational interactions. The **Redline Agent** applies enterprise rules instantly, flags unacceptable clauses, and suggests aligned alternatives. **AI-Generated Playbooks** convert real contracts, past negotiations, and expert guidance into structured playbooks within minutes, giving enterprises clear rules and fallbacks even when no formal standards existed before. The **Risk Review Agent** explains clauses, compares drafts, and surfaces insights in plain language.  
**Best for:** Enterprises already using Icertis CLM wanting AI-driven clause intelligence and playbook creation tied to their contract data.

### Ironclad Clause Library
**Type:** Clause bank with template integration
Ironclad provides a clause library that supports template and workflow authoring, with the ability to store approved clause variants and fallback positions. The **Contract Review Agent** redlines against playbooks and precedents, with clause-level changes displayed as highlighted redlines for review. **Precedent-based redlining** (invitation-only) allows executed agreements from the repository to serve as context. Playbook setup requires an Ironclad Services engagement to translate guidance and clause banks into an Agent-ready playbook.  
**Best for:** Ironclad CLM customers wanting clause management tightly integrated with their template and approval workflows.

### DocuSign CLM Clause Library
**Type:** Clause library within Salesforce-integrated CLM
DocuSign CLM includes a clause library that enables **legal-defined fallback clauses** for negotiations, with centralized access to approved language during contract generation. It supports document generation from Salesforce data using pre-defined templates, with version control and redlining. The clause library is part of a broader CLM workflow including approval routing and a searchable agreement repository.  
**Best for:** Salesforce organizations wanting clause management embedded in their contract generation and negotiation workflows.

### Conga Clause Library
**Type:** Clause library with document generation
Conga provides a clause library within its contract lifecycle management and document generation platform, enabling teams to store, categorize, and insert approved clauses into generated documents. It is positioned for organizations wanting standardized clause language applied consistently across high-volume contract generation.

### Agiloft Clause Library
**Type:** Clause library with AI review and fallback suggestions
Agiloft provides clause-level management within its CLM platform, with **AI-assisted review** that detects risky and non-standard terms and **auto-suggests fallback language** in seconds. Pre-built templates include approved language, and AI-powered contract analysis uncovers obligations and risks. Post-signature obligation tracking is also supported.  
**Best for:** Organizations wanting AI-assisted clause review with fallback suggestions and broad integration coverage.

### CobbleStone Clause Management
**Type:** Clause and template management within CLM
CobbleStone Contract Insight provides clause and template management as part of its contract lifecycle management platform, with version control, approval workflows, and reporting. It is positioned for public sector and mid-market organizations wanting structured clause governance.

### Robin AI Clause Library
**Type:** Conversational clause analysis with citations
Robin AI provides conversational contract analysis where every answer includes **clickable citations linking directly to the clause or provision** in the source document. Users can select document sets using filters before asking questions, enabling clause comparison and deviation analysis across document families. The platform emphasizes verifiability—every answer can be traced to its source clause.  
**Best for:** Legal teams wanting conversational clause analysis with strong citation-based verification.

---

## 🟩 Open-Source Software

Self-hosted, community-driven clause management tools. The open-source ecosystem is **nascent**, with most projects focused on template composition, contract structuring, and AI-assisted CLM rather than dedicated clause libraries.

### template-vault
**Stack:** Python / Git | **License:** Open Source (PyPI)
template-vault is a CLI tool that stores legal templates and clause language as **plain files in a Git repository**, with multi-user sync via `git pull` / `git push` . Key clause-related capabilities:
- **Clause-level composition**: A template can fork a base template and **swap clauses from other templates**, recording provenance in `clause_overrides` 
- **Provenance tracking**: The `upgrade` command knows which clauses were locally modified and leaves them untouched when the parent template gets a new version 
- **Searchable metadata**: Each template has a `meta.json` capturing category, jurisdiction, tags, and summary; the `find` command searches by category, tag, jurisdiction, or keyword 
- **LLM recommendation (opt-in)**: Can ask an LLM for a recommendation, metadata-only by default, but the CLI does not generate new clause text 

**Trade-off:** It is a CLI tool with no web UI—clause management is file-based and Git-native, requiring technical comfort.  
**Best for:** Legal ops teams and developers wanting Git-native clause composition with provenance tracking and no database dependency.

### draftLegal
**Stack:** TypeScript / Python / Docker | **License:** AGPL-3.0
draftLegal is positioned as the open-source alternative to Ironclad + Harvey, with clause-level intelligence as a core capability . Key clause-related features:
- **Extract + cite**: Clauses, dates, and values are extracted, risk-scored, and **cited to the clause and section they came from**; for PDFs the citation opens the original page 
- **Redline & negotiate**: Conservative/moderate/aggressive counter-proposals with **exact replacement language**, applied in a click 
- **Playbook-aligned drafting**: AI agents run at every step with ~30 tools over contracts, including clause search, comparison, and redline 
- **Portfolio intelligence**: Hybrid retrieval across the contract portfolio to answer questions about clause exposure and counterparty terms 

**Trade-off:** Early-stage project; review repository status before production use.  
**Best for:** Teams wanting a self-hosted, AI-native CLM with clause-level extraction, citation, and redline generation, accepting early-stage maturity.

### Codify Core
**Stack:** Python / Akoma Ntoso XML | **License:** Apache-2.0
Codify Core converts legal documents into **structured, machine-readable data** that can be inspected, searched, and reused, preserving articles, sections, tables, and references with anchors and validation findings . For clause management, it provides:
- **Structured extraction**: Each ingestion preserves document structure with coverage counts and validation findings 
- **Akoma Ntoso 3.0 output**: A standard XML format for legal documents, enabling clause-level addressing and reuse 
- **Python library, CLI, REST API, and MCP server**: Multiple access paths for integration 

**Important:** Structural checks do not establish legal accuracy, and jurisdiction configurations are not complete legal corpora.  
**Best for:** Teams needing structured, standards-based ingestion of legal documents with clause-level addressing, particularly for legislation and structured contract types.

### OpenCLM
**Stack:** TypeScript / PostgreSQL / Docker | **License:** AGPL-3.0
OpenCLM is an open-source, self-hostable CLM platform with **clause and template management** as a core feature . Key capabilities include:
- **Clause and template management**: Store, organize, and reuse approved clause and template language 
- **Collaborative redlining**: Review and negotiate contract changes with tracked revisions 
- **Review workflows and approvals**: Route contracts through defined approval chains 
- **Contract repository and deadlines**: Centralized storage with obligation tracking 

**Important status:** Early development release—the signature is an ordinary electronic signature, not advanced or qualified.  
**Best for:** Teams wanting a self-hosted CLM foundation with clause and template management, accepting early-stage maturity.

### contract-vault
**Stack:** Python / Git | **License:** Open Source (PyPI)
contract-vault is the post-signature sibling to template-vault, storing executed contracts in a Git-backed vault with **obligation tracking** rather than clause composition . While not a clause library, it complements template-vault by capturing the obligations and terms that result from executed clause language, with every field carrying its `source` and confidence.  
**Best for:** Teams pairing template-vault's clause composition with post-signature obligation tracking in a Git-native workflow.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Clause Library | Fallback Positions | AI-Assisted | Self-Hosted | Best For |
|----------|---------|-------|----------------|---------------------|-------------|-------------|----------|
| **Icertis** | Proprietary | Cloud | ✅ | ✅ AI playbooks | ✅ Redline Agent | ❌ | Enterprise AI clause intelligence |
| **Ironclad** | Proprietary | Cloud | ✅ | ✅ Precedent-based | ✅ Review Agent | ❌ | Template + clause integration |
| **DocuSign CLM** | Proprietary | Salesforce | ✅ | ✅ Legal-defined | (Check) | ❌ | Salesforce contract generation |
| **Conga** | Proprietary | Cloud | ✅ | (Check) | (Check) | ❌ | High-volume document generation |
| **Agiloft** | Proprietary | Cloud/On-prem | ✅ | ✅ AI fallback | ✅ | (On-prem) | AI review + fallback suggestions |
| **Robin AI** | Proprietary | Cloud | (Analysis) | (Comparison) | ✅ Citations | ❌ | Conversational clause verification |
| **template-vault** | Open Source | Python/Git | ✅ Clause swap | ✅ `clause_overrides` | ✅ Optional LLM | ✅ | Git-native clause composition |
| **draftLegal** | AGPL-3.0 | TypeScript/Docker | ✅ Extract + cite | ✅ Counter-proposals | ✅ AI agents | ✅ | AI-native clause extraction |
| **Codify Core** | Apache-2.0 | Python/Akoma Ntoso | ✅ Structured | ❌ | ❌ | ✅ | Standards-based structuring |
| **OpenCLM** | AGPL-3.0 | TypeScript/Postgres | ✅ Management | (Check) | (Check) | ✅ | Self-hosted CLM foundation |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Legal Clause Library or Standard Clause tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

**Note on the open-source ecosystem:** The open-source landscape for **legal clause libraries** is **very limited and fragmented**. **template-vault** is the most purpose-built open-source tool for clause composition, offering Git-native clause swapping with provenance tracking—a genuinely novel approach compared to commercial platforms . **draftLegal** provides the strongest AI-native clause extraction and redline generation, with citations back to source clauses . **Codify Core** fills the standards-based structuring niche with Akoma Ntoso output for machine-readable legal documents . **OpenCLM** offers clause and template management as part of a broader self-hosted CLM foundation, though it is early-stage . Commercial platforms like Icertis and Ironclad remain far more capable for enterprise clause governance with AI-generated playbooks, precedent-based redlining, and deep integration with contract workflows.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
