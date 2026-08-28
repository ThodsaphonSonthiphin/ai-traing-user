# Context

The ubiquitous language of this repo. A glossary and nothing else - no
implementation detail and no decisions. Decisions live in `docs/adr/`.

## Learner

A project engineer who consults for factories. Not a software engineer. Their
daily tools are office documents, spreadsheets and CAD, not a terminal or a
repository. Every course choice is measured against what this person can do
unaided.

## Hat

One of the three roles a Learner plays in the same working day:

- **selling** - proposals, RFQ replies, cost estimates
- **delivering** - specs, BOQ, drawing notes, factory data analysis
- **documenting** - site reports, progress reports, minutes

Deliberately not "role": a Learner wears all three, often in one day, so the
course teaches all three rather than specialising in one.

## Deliverable

A document the Learner gives to a client in the course of their own work - a
proposal, a spec, a site report, a costed BOQ. Always the Learner's own client
artifact. The word is never used for something the course itself requires them
to produce, and a Lab is built around a Deliverable rather than creating one.

## Surface

One entry point into Claude, as a Learner would see it - Claude Cowork, Claude
Code (its CLI or its VS Code extension), claude.ai on the web, the Claude
desktop app, or the Claude Chrome extension. Surfaces are what a Learner opens,
not what Anthropic ships: Cowork and Claude Code share one engine but are two
Surfaces, because a Learner opens them differently and has to learn each
separately.

## Spine

The one Surface a Learner works in for the whole course and is expected to keep
opening afterwards. Distinct from a Surface *shown for contrast*, which the
course demonstrates once and never builds on. A course has exactly one Spine.

## Connector

A signed-in link from a Surface to an external system - Microsoft 365, Google
Drive - through which Claude reaches material the Learner did not put on their
own machine. Deliberately not a synonym for "how Claude reads my files": a
Working folder needs no Connector and no sign-in, which is the distinction the
course depends on.

## Working folder

The one folder on the Learner's own machine that Cowork reads and writes
directly. It holds the Learner's real client work, and it is what a Lab operates
on. Named separately from a Connector because the two reach material by
different routes and fail for different reasons.

## Lab

One exercise a Learner performs on their own real client work. The steps and the
definition of done are fixed by the course; the material is the Learner's own.
That split is what separates a Lab from a demonstration.

## Setup

The one sitting that takes a Learner from a bare Mac to a working Claude,
before any teaching starts. Deliberately not a Lab: it operates on the cloned
course repository rather than the Learner's own client work, which is the
distinction the word Lab exists to carry. The course has one Setup and five
Labs.

## Capstone

The single Skill a Learner produces from their own repeatable job, at the end of
the course. It is the pass evidence: the course has not landed unless the
Learner holds one that works on their real work.

## Skill

A named, reusable instruction set a Learner invokes by asking for it in ordinary
words. Two authoring routes exist and they are not interchangeable - one is
recorded by demonstration, one is written as a file - so "write a Skill" is
always qualified by which route.
