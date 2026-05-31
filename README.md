# 🐙 Welcome to `fuentesjr/.github`

This is the friendly little control room for GitHub defaults across `@fuentesjr` repositories. When a repository does not provide its own local template, GitHub can borrow the shared files here so every project starts with a little more structure and a lot less copy-paste.

## ✨ What this repo does

This repository holds reusable GitHub community files: pull request templates, issue templates, and other shared project guidance. Think of it as a cozy Octocat backpack full of defaults for the rest of the account.

## 🧰 What lives here

- `.github/PULL_REQUEST_TEMPLATE.md` — a risk-aware PR template that helps authors and reviewers build shared understanding before merge.
- `.github/ISSUE_TEMPLATE/incident_review.md` — a blameless, systems-focused incident review template for learning from surprises without turning them into fault hunts.

## 🪄 How GitHub uses it

GitHub treats a repository named `.github` as special. Files in this repo can become account-level defaults for other repositories when those repositories do not define their own versions.

Local repository files still win. If a project needs a more specific template, it can add its own and GitHub will use that instead.

## 📝 Template philosophy

The templates here are intentionally lightweight, friendly, and practical. They are designed to encourage good judgment without creating checkbox theater.

They aim to help people answer:

- What changed?
- What risk does this carry?
- What signal do we have?
- How would we detect or recover from trouble?
- What can the system teach us next time?

## 🧭 Working agreements

A few principles guide the defaults in this repo:

- Prefer clarity over ceremony.
- Prefer learning over blame.
- Prefer small, focused changes over mystery boxes.
- Prefer structural fixes over repeated symptom patches.
- Keep things as simple as possible, but not simpler.

## 🚀 Using these defaults

Most repositories do not need to do anything. If they do not have their own matching GitHub template, GitHub can fall back to the one here.

If a repository has special needs, add a local template there. The local version should be treated as the project-specific source of truth.

## 🌱 Growing this garden

This repo should stay small and useful. Add shared defaults only when they help more than one project, and keep the tone welcoming enough that future contributors feel invited rather than inspected.

When in doubt: make the helpful path the easy path. ✨
