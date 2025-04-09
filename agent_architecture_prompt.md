# 🧠 Agent Framework & Ingestor Agent Implementation

You are designing a multi-agent LLM system that solves real-world data ingestion, risk modeling, and decision-making across complex infrastructure systems.

Your goal is to:
- Define a repeatable architecture for building robust, validated agents.
- Include schema constraints, fallback paths, tool access, and explainability.
- Start with the simplest agent: the Ingestor-Resolver Agent.

## ⚙️ MASTER AGENT SYSTEM DESIGN

### 1. Define the Global Architecture
- Use a meta-controller (Executor Agent) to validate schema, monitor flow, retry on failure.
- Each agent should:
  - Have a single responsibility (SRP)
  - Be backed by tools (OCR, fuzzy match, plugins)
  - Have LLM only for structured extraction, not decision-making
  - Be schema-constrained

### 2. Agent Roles (Enumerate)

| Agent Name | Function |
|------------|----------|
| Ingestor-Resolver Agent | Parse docs and resolve entities |
| Risk & Graph Analyst Agent | Score risk and update the graph |
| Simulation Strategist Agent | Run time-based cascading simulations |
| Ops & Insights Agent | Summarize, answer queries, monitor dashboard |
| Executor Agent | Orchestrate flow, validate schemas, fallback logic |

---

## 🧾 SUB-PROMPT: INGESTOR-RESOLVER AGENT (FULL BUILD)

You are now building the **Ingestor-Resolver Agent**.

This agent will:
- Accept `.pdf`, `.docx`, or `.txt` files
- Extract named entities (Supplier, Component, Facility, etc.)
- Resolve to canonical form using fuzzy matching and ID lookup
- Output structured JSON with provenance, confidence, and resolution method

### Design the following:

#### 1. File Type Handling
- Use pdfplumber for `.pdf`, python-docx for `.docx`, and open/read for `.txt`.

#### 2. Entity Types
- Supplier (name, ID, address), Part (name, criticality), Owner (jurisdiction)

#### 3. Extraction Method
- LLM (GPT-3.5 or 4o) in function-calling mode
- Schema-constrained output
- Include part supplied, contract ID, supplier name, address

#### 4. Resolution Logic
- Use fuzzywuzzy or SBERT to match aliases (e.g., L&T → Larsen & Toubro)
- Normalize addresses
- Output resolved_name and confidence

#### 5. JSON Output Schema
```json
{
  "suppliers": [
    {
      "name": "L&T",
      "resolved_name": "Larsen & Toubro Ltd",
      "confidence": 0.95,
      "part_supplied": "Forged Casings",
      "contract_reference": "MOD/ORD/334",
      "source": "contract_sample_1.pdf"
    }
  ]
}
```

#### 6. Enhancements
- Handle black/white scanned PDFs via OCR fallback
- Process folders of files
- Store `.json` and update `all_suppliers.csv` (one master result)
- Support `.txt` and `.docx`
- Add resume capability (processed_files.txt)

---

## ✅ CHECKPOINT FOR NEXT AGENTS

When finished with the Ingestor Agent, validate:

1. All test files produce correct structured JSON
2. `.csv` output aggregates all files
3. Script supports new files without re-processing
4. Cost control is enabled (gpt-3.5 or 4o used)
5. JSONs are stored per file for debugging

Only then proceed to build the **Risk & Graph Analyst Agent**.
