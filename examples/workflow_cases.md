# Workflow Examples

---

## Example 1 — Missing Information

Input:

```
intake_status = missing_information
coverage_likelihood = unknown
```

Next Action:

```
request_information
```

---

## Example 2 — Likely Covered

Input:

```
intake_status = complete
coverage_likelihood = likely_covered
```

Next Action:

```
route_to_decision_engine
```

---

## Example 3 — Uncertain Case

Input:

```
intake_status = complete
coverage_likelihood = uncertain
```

Next Action:

```
escalate_specialist
```
