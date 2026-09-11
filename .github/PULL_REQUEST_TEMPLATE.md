<!--
LEGEND: ✍️ = author (usually an agent) fills before requesting review.
        👀 = human reviewer only. Agents never tick a 👀 box; a pre-ticked box is a defect.
These fields record work done to build shared understanding, not guarantees.
They are not used to assign fault.

Author rules:
- Answer from the diff and the repo only. Never guess.
- Status glyphs are a fixed vocabulary — use only these:
    ✅ yes   ❌ no   ❓ unknown — needs human check   ➖ none / not applicable
- ➖ needs a one-clause reason visible in the diff (e.g. "➖ no files under db/migrate").
- Bullets, not prose. Keep every heading. Leave optional fields blank rather than padding them.
- Agents: copy this file, fill it, and pass it with
  `gh pr create --body-file <file> [--attach <path> ...]`.
-->

## ✍️ Summary

**What changed** (required):
<!-- 1–3 bullets of observable behavior, not a file list -->
-

**Why** (required):
<!-- "Closes #NNN" or a link, or one line. Name dependent PRs and merge order here. -->
-

**Risk tier** (required): 🟢 | 🟡 | 🔴, plus `hotfix` if shipping outside normal cadence
<!-- hotfix = reviewer reads Recovery first.
     Grade from the diff. Highest match wins:
     🔴 touches any of: db/migrate or a data backfill; auth, authorization, sessions, or
        permissions; a billing, payment, or ledger write path; secrets or credentials;
        an external integration
     🟡 any other change to existing behavior, including a shared model, controller,
        job, or service used by more than one flow
     🟢 no change to existing behavior: additive and behind a flag, isolated new code
        with no changed callers, view-only, test-only, or docs
     Then name what is touched: endpoints, models, jobs, integrations. -->
-

**Review focus** (required):
<!-- files or lines carrying the real risk, in read order. "➖ mechanical" is valid -->
-

**Walkthrough** (optional; expected when UI changed, or ≥3 of models, jobs, controllers, services touched):
<!-- One artifact, chosen by shape of the change: a screenshot from a system test for a
     single view (before and after if changed); a video from the system test for a
     multi-step UI flow; a Mermaid sequence or flow diagram generated from the diff
     for a cross-cutting change. Reference files by local path, e.g. ![after](./tmp/after.png),
     and pass each with `gh pr create --attach <path>`; gh rewrites the path to the
     uploaded asset. If none applies, leave blank. Do not manufacture one. -->

**Dependencies** (required): ➖ no lockfile diff | added, upgraded, or removed, with versions

**Unrelated changes in this diff** (required): ➖ none | list, with reason
<!-- drive-by fixes, formatting, renames. Prefer splitting them into their own PR. -->

**Out of scope / not done** (optional):
<!-- deliberate omissions so the reviewer does not chase them -->

## ✍️ Verification

**Tests added or changed** (required):
<!-- paths; "➖ reason" is valid -->

**Ran locally** (required):
<!-- exact command and result, e.g. `bin/rails test test/models/x_test.rb` → 12 runs, 0 failures.
     Include the CI status if known: green, red with reason, or not yet run. -->

**Not verified** (required):
<!-- what only a human or production can confirm. "➖ nothing" is valid -->

## ✍️ Recovery

**Recovery needed** (required): ➖ 🟢, no change to existing behavior | see below
<!-- 🟢: this line is the whole section; leave the fields below blank.
     🟡: fill the fields marked 🟡🔴. 🔴: fill every field. Every field accepts ❓. -->

**💥 Worst case** (🟡🔴 required):
<!-- one line: what breaks for whom if this is wrong -->

**↩️ Revert safety** (🟡🔴 required): ✅ | ❌ reason | ❓
<!-- Does `git revert <merge>` alone restore prior behavior? Usually ❌ if schema or
     data changed, jobs were enqueued with new args, or dependencies changed. -->

**🗄️ Schema** (🔴 required): ➖ no files under db/migrate | see below
- Migration(s):
- Reversible (`down` defined and meaningful): ✅ | ❌ | ❓
- `down` tested locally (`db:migrate:redo`): ✅ | ❌
- Safe while old code is live: ✅ | ❌ reason | ❓
  <!-- locks, NOT NULL, renames, defaults on big tables, and old code still writing
       to the changed table -->
- Writers that bypass model validations on the changed table (`insert_all`, `upsert`, raw SQL): ➖ grep result | list
<!-- PROJECT (unset at org level): migrations run [before new code boots | after | manually].
     Until the repo sets this, answer "safe while old code is live" as ❓. -->

**📦 Data** (🔴 required): ➖ no writes outside normal app paths | see below
- What is changed or backfilled:
- Idempotent, safe to re-run: ✅ | ❌ | ❓
- Repair path if wrong:

**⚙️ Jobs** (🟡🔴 required): ➖ no changes to app/jobs, app/sidekiq, or `perform` signatures | see below
- Job(s) affected:
- Queued jobs with old args or an old class name run under new code: ✅ | ❌ | ❓
- New-arg jobs run under old workers mid-deploy: ✅ | ❌ | ❓

**🔌 Kill switch** (🟡🔴 required): flag or config name and where it is read | ➖ reason

**⏪ Rollback** (🟡🔴 required):
<!-- exact command(s), in order, for this deploy target; include migrate:down if schema changed.
     Infer the target from the repo: config/deploy.yml → `kamal app rollback <version>`;
     Procfile or app.json → `heroku rollback vNNN -a <app>`. Neither found → ❓. -->

**📡 How we'd detect it** (🟡🔴 required):
<!-- only signals present in the diff or repo: a log line, error class, metric, or alert.
     "❓ no signal in the diff or repo" is valid and tells the reviewer to name one. -->

## 👀 Reviewer

<!-- Human only. Tick each box after doing the work it names. -->

- [ ] **Risk tier** is right and **Unrelated changes** is ➖ or acceptable. If not, ask the author to fix before reading further.
- [ ] Read **Review focus** in the order given.
- [ ] Every ❓ and every **Not verified** item is checked by me or explicitly accepted in a comment.
- [ ] 🟡🔴 only: **Worst case**, **Rollback**, and **How we'd detect it** are believable for this deploy target.
