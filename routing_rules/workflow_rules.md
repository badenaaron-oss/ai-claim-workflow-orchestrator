# Workflow Routing Rules

The Workflow Orchestrator determines the next step in the claim lifecycle.

---

## Rule 1

If:

```
intake_status = missing_information
```

Then:

```
next_action = request_information
```

---

## Rule 2

If:

```
coverage_likelihood = likely_covered
```

Then:

```
next_action = route_to_decision_engine
```

---

## Rule 3

If:

```
coverage_likelihood = uncertain
```

Then:

```
next_action = escalate_specialist
```

---

## Rule 4

If:

```
coverage_likelihood = unknown
```

Then:

```
next_action = request_information
```
