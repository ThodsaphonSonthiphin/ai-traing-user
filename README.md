# Claude course for factory consulting engineers

A live-taught workshop that gets a project engineer who consults for factories
using Claude across selling, delivering and documenting the work, and writing
their own working Skill.

This repository is the course's **thinking**, not yet its handouts. Most of what
is here is the record of decisions taken so far and the ones still open.

- Course material is written in **English**.
- The working conversation with the owner is in **Thai**.

## Where things live

| Path | What it holds |
| --- | --- |
| [CONTEXT.md](CONTEXT.md) | The glossary - the repo's ubiquitous language. Terms only: no decisions, no implementation. |
| [docs/adr/](docs/adr/) | One file per decision, each recording the options that lost. |
| [docs/decision-map/claude-for-factory-consultants/](docs/decision-map/claude-for-factory-consultants/) | The decision map for the whole effort: [map.md](docs/decision-map/claude-for-factory-consultants/map.md) plus one ticket per decision under `tickets/`. |
| [CLAUDE.md](CLAUDE.md) | The instructions Claude loads in every session in this repo. |

## Where the work stands

The map carries one milestone, `report-pitch` - *a Learner produces a
client-facing report and pitch for a consulting, management or business-analysis
engagement*. All ten tickets assigned to it are closed, as are three tickets that
predate the milestone and are still unassigned. Eleven ADRs came out of that,
`claude-course-0001` through `claude-course-0011`.

Three of the sixteen tickets are still open:

- [`repo-layout`](docs/decision-map/claude-for-factory-consultants/tickets/repo-layout.md) - how the course is laid out so it is teachable from a clone.
- [`capstone-spec`](docs/decision-map/claude-for-factory-consultants/tickets/capstone-spec.md) - what the Learner's Capstone Skill must satisfy.
- [`chrome-extension-usecases`](docs/decision-map/claude-for-factory-consultants/tickets/chrome-extension-usecases.md) - which named browser use cases the Chrome extension is taught through.

The `Not yet specified` section of the map is the fog list - things known to be
undecided but not yet worth a ticket.

**This file deliberately does not fix the learner-facing structure of the repo.**
That is `repo-layout`'s question, and it is still open. Anything here describes
the repo as it is for whoever is *building* the course.

## Working the map

One decision per session, through the `decision-map` plugin:

```
/decision-map:work            # show the frontier, claim ONE ticket, resolve it, stop
/decision-map:chart           # turn something from the fog list into new tickets
```

Where a closed ticket produced an ADR, the ADR is the record and the ticket's
gist is only a summary of it. Two closed tickets have no ADR - `account-plan`
and `existing-material` - and `account-plan`'s gist is superseded by the cohort
facts below.

## Setup for working on this repo

The `/decision-map:*` commands come from the `decision-map` plugin in the
`workflow-daily-work` marketplace. [.claude/settings.json](.claude/settings.json)
lists it under `enabledPlugins`, but that key only switches a plugin **on** - it
does not install it. Install it once per machine:

```sh
claude plugin marketplace add ThodsaphonSonthiphin/workflow-daily-work
claude plugin install decision-map@workflow-daily-work
```

Then restart the Claude Code session.

### Fix: `/decision-map:work` does not exist

Symptom - the commands do not autocomplete, `chart-map` and `work-map` are not
in the session's skills, and reopening VS Code changes nothing.

1. **Confirm what is actually installed.**

   ```sh
   claude plugin list
   ```

   Read the result carefully, because the two failures look nothing alike:

   - the plugin is **missing from the list entirely** - it was never installed;
     continue at step 2.
   - the plugin is listed with **`Status: ✘ disabled`** - it is installed but
     switched off; skip to step 5.

2. **Confirm the marketplace is registered.**

   ```sh
   claude plugin marketplace list
   ```

   If `workflow-daily-work` is absent, add it:

   ```sh
   claude plugin marketplace add ThodsaphonSonthiphin/workflow-daily-work
   ```

3. **Do not trust the cache as evidence.** `~/.claude/plugins/cache/` can already
   hold the plugin's full source - commands, skills and all - while the plugin is
   still not installed. The file that decides is
   `~/.claude/plugins/installed_plugins.json`; if the plugin has no entry there,
   nothing loads it.

4. **Install it.**

   ```sh
   claude plugin install decision-map@workflow-daily-work
   ```

   Add `-y` when stdout is not a TTY - which includes running the command from
   inside a Claude Code session. The default scope is `user`, which records the
   install in your home directory and leaves this repo's
   [.claude/settings.json](.claude/settings.json) untouched.

5. **Switch it on**, if step 1 showed it installed but disabled. Either add it to
   `enabledPlugins` in [.claude/settings.json](.claude/settings.json), or:

   ```sh
   claude plugin enable decision-map@workflow-daily-work
   ```

6. **Restart the Claude Code session.** An install never applies to the session
   that ran it.

7. **Verify.** `claude plugin list` shows `Status: ✔ enabled`, and
   `/decision-map:work` autocompletes.

This repo's `enabledPlugins` names four plugins from the same marketplace -
`decision-map`, `dev-workflows`, `github-backlog` and `react-workflows`. Each one
is installed separately, by the same steps.

## Conventions

- **ADR prefix.** This repo owns one ADR sequence, prefixed `claude-course`.
  Files are `docs/adr/claude-course-NNNN-<slug>.md`; citations are
  `claude-course-0001`, never a bare number. Existing files are not renamed.
- **A superseded decision is amended, not rewritten.** ADRs carry dated
  amendments when a later decision moves them.
- **Terms go in CONTEXT.md before they are used as terms.** Several decisions
  turned on splitting one overloaded word into two - `Connector` and
  `Working folder`, `Lab` and `Setup`.

## Fixed facts about the cohort

Learners are on **individual Max plans, Mac machines, Chrome**. Not Team, not
Enterprise, not company-managed. Two consequences bite constantly:

- Max is a **consumer** plan: the training toggle is per learner and there is no
  admin lever to set it for the cohort.
- Recording a Skill is available on Pro/Max/Team in Cowork in Claude for Mac, and
  is unavailable on Windows and on Enterprise - so it is open to this cohort and
  would not be to most others.

The Spine of the course is **Claude Cowork in the desktop app**
(`claude-course-0001`). The Learner is not expected to open a terminal, which is
why the author clones this repo onto their machine for them
(`claude-course-0004`).
