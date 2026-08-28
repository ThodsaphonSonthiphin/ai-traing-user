---
title: Lab pattern - how is a lab repeatable when every learner brings different input?
type: grilling
mode: HITL
status: open
assignee: 
blocked_by: [session-shape, confidentiality-rule]
gist: 
---

## Question

How is a lab written so it stays repeatable and checkable when every learner supplies different input - what is fixed (the steps, the checks, the definition of done) and what varies (their own document or data)?

<!-- decision-map:graph:start -->
```mermaid
graph TD
    ME["lab-design-pattern (this ticket)"]
    P0["confidentiality-rule"] --> ME
    P1["session-shape"] --> ME
    ME --> C0["capstone-spec"]
    ME --> C1["chrome-extension-usecases"]
    ME --> C2["design-deliverable"]
```
<!-- decision-map:graph:end -->
