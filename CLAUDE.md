# Claude course for factory consulting engineers

A live-taught workshop that gets a project engineer who consults for factories
using Claude across selling, delivering and documenting the work, and writing
their own working Skill. Course material is written in **English**; the working
conversation with the owner is in Thai.

## ADR sequence

This repo owns one ADR sequence and its prefix is **`claude-course`**. Every ADR
filename opens with it - `docs/adr/claude-course-NNNN-<slug>.md` - and every
citation carries it: `claude-course-0001`, never a bare number. Do not ask for
this prefix again, and do not rename existing files.

## Where things live

- `CONTEXT.md` - the glossary. Terms only: no decisions, no implementation.
- `docs/adr/` - one file per decision, each recording the options that lost.
- `docs/decision-map/claude-for-factory-consultants/` - the decision map for the
  whole effort. Work it one ticket per session with `/decision-map:work`; chart
  new tickets out of the fog list with `/decision-map:chart`.

## Fixed facts about the cohort

Learners are on **individual Max plans, Mac machines, Chrome**. Not Team, not
Enterprise, not company-managed. Two consequences bite constantly, so check them
before proposing anything:

- Max is a **consumer** plan: the training toggle is per learner and there is no
  admin lever to set it for the cohort.
- Recording a Skill is available on Pro/Max/Team in Cowork in Claude for Mac, and
  is unavailable on Windows and on Enterprise - so it is open to this cohort and
  would not be to most others.
