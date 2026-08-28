---
title: Coverage - which Claude functions are taught hands-on versus shown as reference?
type: grilling
mode: HITL
status: closed
assignee: coverage-1512
blocked_by: [existing-material, surface-choice]
gist: Lab time is earned by serving the report-pitch milestone: connectors, Projects, outputs, Design, then Skills. Sub-agents, scheduled tasks and plugins are demo-only.
---

## Question

Which Claude functions are taught hands-on with a lab, which are demonstrated as reference only, and which are left out of the course entirely - across skills, subagents, MCP, hooks, plan mode, memory, artifacts, Claude Design, and Projects?

<!-- decision-map:graph:start -->
```mermaid
graph TD
    ME["function-coverage (this ticket)"]
    P0["existing-material"] --> ME
    P1["surface-choice"] --> ME
    ME --> C0["capstone-spec"]
    ME --> C1["session-shape"]
```
<!-- decision-map:graph:end -->

<!-- decision-map:resolution:start -->
## Resolution

Lab time is earned by serving the report-pitch milestone: connectors, Projects, outputs, Design, then Skills. Sub-agents, scheduled tasks and plugins are demo-only.

Detail: docs/adr/claude-course-0002-coverage-ordered-by-first-milestone.md

```mermaid
flowchart TD
    RULE["RULE - lab time is earned by serving<br/>the report-pitch milestone,<br/>not by what the product ships"]
    RULE --> LAB["HANDS-ON LAB, in the order a Learner<br/>meets them while making one real report"]
    LAB --> L1["1 Connectors + local files"]
    L1 --> L2["2 Projects + memory"]
    L2 --> L3["3 Professional outputs<br/>Excel with formulas, PPT, documents"]
    L3 --> L4["4 Claude Design - the pitch"]
    L4 --> L5["5 Skills - the Capstone"]
    RULE --> DEMO["DEMO ONLY<br/>sub-agents · scheduled tasks ·<br/>plugins · Chrome extension"]
    RULE -.->|displaces| TOUR["a feature tour of Cowork,<br/>and any ordering by raw power"]
    OUT["NOT ON THE SPINE - no decision needed<br/>hooks · plan mode · Claude Code CLI"]
```

## The re-scope this ticket needed

The Question as charted asked which functions are taught "across skills,
subagents, MCP, hooks, plan mode, memory, artifacts, Claude Design, and
Projects". That list was written while a Claude Code Spine was still assumed. Two
of its entries - **hooks** and **plan mode** - are Claude Code concepts that do
not appear anywhere in Cowork's documented capabilities, so they are not choices;
and the list **omitted scheduled tasks entirely**, which is plausibly the
single highest-value function in the product for a consultant who files recurring
reports. The list was rebuilt against Cowork's own documentation before anything
was tiered.

## The deciding move

The owner named the first milestone during this session: **a client-facing report
and pitch, for consulting, management and business-analysis work.** That converted
coverage from an open ranking problem into an ordering one - a function earns a
Lab if a Learner needs it to carry one real report end to end, and waits
otherwise. It also settled the one question this session could not answer on its
own: scheduled tasks is demo-only, because it automates a workflow that must
already be stable, and nothing is stable during the course that creates it.

## Skills lands last, deliberately

The Capstone records a repeatable job. A Learner has no repeatable job in Claude
on day one - they have one only after steps 1 to 4 have carried a real report to
a client. Teaching Skills earlier would have them record a workflow they have not
yet performed.

## Confirming exchange

Presented with the tiering and asked whether scheduled tasks should earn a full
Lab or close the course as a demo, and whether anything in the grouping should
move, the owner answered by naming the first milestone instead: **"miletone แรก
จาก user คือ ทำ report pitch ลูกค้า Consult, บริหาร วิเคราะห์ ธุรกิจ"**. Shown
the coverage re-ordered against that milestone, together with the proposed
milestone membership, the owner answered **"ok"**.

## What this hands to other tickets

- `session-shape` - the Lab list is now ordered and countable, which is the input
  a session count was waiting on.
- `capstone-spec` - Skills is taught last, on a workflow the Learner has just
  performed. The fallback path also gained a step: Cowork does not read the
  Claude Code CLI's `~/.claude` directory, so a `SKILL.md` written there must be
  added in **Customize** before it is usable.
- `chrome-extension-usecases` - the Chrome extension pairs with Cowork by design
  rather than competing with it, which softens the overlap flagged in
  `claude-course-0001`.
- `design-deliverable` - Claude Design's Lab is step 4, and its deliverable is the
  pitch the client sees.

<!-- decision-map:resolution:end -->
