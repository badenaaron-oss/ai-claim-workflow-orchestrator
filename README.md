# 🚦 AI Claim Workflow Orchestrator

An AI workflow agent that routes insurance claim cases through intake, validation, decision, and communication systems.

This system determines **what happens next in the claim process** based on structured claim data.

## Multi-Agent System Overview

This project is part of a multi-agent AI workflow for handling insurance claim inquiries.

The system separates **data intake, safety controls, workflow routing, deterministic decisions, and customer communication**.

```mermaid
flowchart TD

A[Policyholder Inquiry]

subgraph AI Agents
B[AI Claim Intake Assistant]
E[🚦 Claim Workflow Orchestrator]
F[Coverage Explanation Assistant]
end

subgraph Safety Layer
C[Input Sanitation + Validation]
D[Structured Claim Data]
end

subgraph Deterministic Decision Layer
G[Coverage Decision Engine]
H[Structured Decision Output]
end

subgraph Customer Communication
I[PHONE_SCRIPT]
J[EMAIL_RESPONSE]
K[INTERNAL_SUMMARY]
end

A --> B
B --> C
C --> D
D --> E

E --> G
G --> H

H --> E

E --> F

F --> I
F --> J
F --> K

%% styling

classDef ai fill:#ffe599,stroke:#333,stroke-width:2px
classDef orchestrator fill:#f6b26b,stroke:#333,stroke-width:4px
classDef safety fill:#d9ead3,stroke:#333,stroke-width:2px
classDef decision fill:#cfe2f3,stroke:#333,stroke-width:2px

class B,F ai
class E orchestrator
class C,D safety
class G,H decision
```

## Example Workflow Decisions

```
missing_information → request documents

likely_covered → route to claim submission

uncertain → escalate to specialist

denied → generate explanation
```

---

## Related Projects

This orchestrator connects two other AI workflow agents:

- **AI Claim Intake Assistant** → collects and sanitizes claim information  
- **Coverage Explanation Assistant** → converts structured decisions into customer explanations
