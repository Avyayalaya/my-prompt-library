# 🧠 Supply Chain Risk Modeling & System Architecture

You are an expert AI systems architect working on designing an LLM-powered system to map and mitigate risks in a complex defense-grade supply chain network.

Your job is to think from **first principles**, explore **systemic risk**, design **data models**, simulate **cascade failures**, and implement the architecture using agents powered by LLMs and deterministic logic.

## 🎯 CHAINED INSTRUCTIONS

### STEP 1: Problem Space Validation
- Define the different classes of risks in multi-tier supply chains (e.g., geopolitical, legal, capacity, quality, substitution).
- List observable and latent risks.
- Include black swan/catastrophic risks, and explain how you might model or simulate them.
- Identify actors and incentives (e.g., government, vendor, OEM, sub-tier supplier).
- Establish the assumption: vendors cannot refuse information requests from government.

### STEP 2: Entity and Data Model
- Define the graph schema for the supply chain.
- Node types: Supplier, Owner, Facility, Component, Risk, Region.
- Edge types: Supplies, Owns, Located_In, Depends_On, Exposes.
- Include metadata like: address, IDs (DUNS, GSTIN), criticality, timestamp, provenance.

### STEP 3: Risk Modeling and Taxonomy
- Create a scoring framework: probability, severity, confidence.
- Define core plugins (e.g., substitution risk, single point failure, compliance, surge capacity).
- Show how LLM can help route to the correct plugin using context.
- Risks must cite source and evidence — no hallucination.

### STEP 4: Simulation Layer
- Model cascading failure across a multi-tier graph.
- Include recovery paths, MTTR, scenario templates.
- Simulate sabotage, overuse, conflict, or supplier removal.
- Define output structure: time series of degradation, impacted systems, suggested actions.

### STEP 5: Visualization and Operator Layer
- Outline dashboards: risk summary, scenario outcomes, decision support.
- Include explainability constraints: all insights must cite source graph, simulation data, or logs.

### STEP 6: Agent Architecture (high level)
- Describe agent orchestration.
- Introduce the concept of a schema-validating, role-restricted, meta-controller (Executor Agent).
- Assign tool access and memory constraints per agent.
- Design flow from ingestion → resolution → risk scoring → simulation → dashboard.

## ✅ Output Required
- A complete visual flow of the architecture (can be described as steps + components).
- Key tradeoffs and how to keep the system robust (hallucination control, fallback logic).
- Testing and validation strategies.
