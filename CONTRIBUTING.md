# 🤝 Contributing

Thanks for helping improve these shared GitHub defaults. This repository is intentionally small: changes here can influence many `@fuentesjr` repositories, so the best contributions are clear, focused, and broadly useful.

## 🧭 Start with the local repo

If you are contributing to another repository, check whether that repository has its own `CONTRIBUTING.md`, issue templates, or pull request template. Local project guidance wins over these shared defaults.

Use this file when the target repository does not provide more specific guidance.

## 🌱 What belongs here

Good candidates for this repo:

- Shared pull request or issue templates.
- Account-level contribution, support, or security guidance.
- Small wording improvements that make the defaults clearer or friendlier.
- Process changes that help multiple repositories, not just one project.

Usually avoid:

- Repo-specific rules or checklists.
- Heavy process for rare situations.
- Automation that every repo would need to opt into separately unless it is clearly reusable.
- New templates that duplicate an existing one with only minor wording changes.

## 🧩 Keep changes focused

Prefer small pull requests with one clear purpose. If a change affects expectations, workflow, security, data, releases, or many repositories at once, open an issue or discussion first so the shape of the change is clear before implementation.

## 🧪 Tests and verification

Use the relevant checks for the repository you are changing. For this repo, that usually means reviewing the rendered Markdown and confirming the file lives in the GitHub-supported location.

In your pull request, say what you verified. If there is no automated check to run, say that too.

## 📝 Pull requests

Use the shared pull request template and choose the risk tier honestly. Highest match wins:

- 🔴 High: touches db/migrate or a data backfill; auth, authorization, sessions, or permissions; a billing, payment, or ledger write path; secrets or credentials; or an external integration.
- 🟡 Medium: any other change to existing behavior.
- 🟢 Low: no change to existing behavior (additive and behind a flag, isolated new code with no changed callers, view-only, test-only, or docs).

Append `hotfix` to the tier if shipping outside normal cadence.

Use ➖ with a one-clause reason visible in the diff when something does not apply. Use ❓ when only a human or production can confirm it.

The 👀 Reviewer checklist is for the human reviewer; authors, including agents, leave it unticked.

The goal is shared understanding, not paperwork.

## 👀 Review culture

Review should improve the system, not assign fault. Helpful review comments are specific, kind, and oriented toward better outcomes.

Prefer feedback that explains:

- What risk or confusion you see.
- Why it matters.
- What would make the change clearer, safer, or simpler.

## 🛡️ Security concerns

Do not open a public issue for a suspected vulnerability, leaked secret, or sensitive data exposure. Use the private reporting path provided by the affected repository. If none exists, contact the repository owner directly before sharing details publicly.

## ✨ Guiding principle

Make the helpful path the easy path. Keep things as simple as possible, but not simpler.
