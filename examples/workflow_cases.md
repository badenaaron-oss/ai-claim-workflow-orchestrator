# Workflow Orchestrator Examples

These examples demonstrate how the Workflow Orchestrator routes cases using **system states**, not policy interpretation.

The orchestrator never evaluates coverage rules.  
It only determines **what step happens next** in the workflow.

---

## Example 1 — Missing Information

### Input State

```
workflow_stage = intake
intake_status = missing_information
decision_status = pending
decision_confidence = unknown
```

### Next Action

```
request_information
```

### Explanation

The claim intake is incomplete.  
The orchestrator routes the case to request additional documentation from the policyholder.

---

## Example 2 — Ready For Decision

### Input State

```
workflow_stage = validation
intake_status = complete
decision_status = pending
decision_confidence = unknown
```

### Next Action

```
route_to_decision_engine
```

### Explanation

All required intake data is present.  
The orchestrator routes the structured claim data to the coverage decision engine.

---

## Example 3 — Manual Review Required

### Input State

```
workflow_stage = decision
intake_status = complete
decision_status = manual_review_required
decision_confidence = low
```

### Next Action

```
escalate_specialist
```

### Explanation

The decision engine determined that the claim requires human review.  
The orchestrator routes the case to a benefits specialist.

---

## Example 4 — Decision Complete

### Input State

```
workflow_stage = decision
intake_status = complete
decision_status = complete
decision_confidence = high
```

### Next Action

```
generate_explanation
```

### Explanation

A decision has been returned by the decision engine with high confidence.  
The orchestrator routes the case to the Coverage Explanation Assistant to generate the customer response.
