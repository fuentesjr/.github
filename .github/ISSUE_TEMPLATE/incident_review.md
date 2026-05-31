---
name: Incident review
about: Review an incident through a blameless, systems-focused lens
title: "[Incident Review] "
labels: incident-review
assignees: ""
---

<!-- LEGEND: This review examines the system that produced the incident, not the people in it.
     We ask what made the failure likely and hard to catch — not who to attribute it to.
     PR checkboxes, approvals, and authorship are NOT used as fault evidence. If review signal
     was insufficient, that is a finding about the review *system*, not about any reviewer. -->

## 📋 Summary
<!-- 2–3 sentences: what happened, observable impact, current status. -->

## 💥 Impact
- **What users/systems experienced:**
- **Scope & duration:** <start → detected → mitigated → resolved>
- **Severity:**

## ⏱️ Timeline
<!-- Factual sequence. Times in UTC. Describe events and signals, not judgments. -->
| Time | Event | Signal available at the time |
|------|-------|------------------------------|
|      |       |                              |

## 🚚 Path to impact
<!-- Trace the path, neutrally. It may be a code change, config change, ops action, external dependency, or process gap.
     The point is to see what the process surfaced and what it didn't.
     Describe what signal existed, not whether someone "should have" seen it. -->
- **What was intended or expected:**
- **What signal was present** (CI, risk tier, blast-radius notes, tests, alerts, runbooks):
- **What signal was absent or misleading:**
- **Where the gap between intent and effect lived:**

## 🏗️ Contributing structure
<!-- The Meadows layer. Look past the triggering event to recurring structure. -->
- **Feedback loops:** <what delayed or hid detection? where was the lag?>
- **Incentives / rules:** <did velocity pressure, tier-inflation avoidance, or norms shape behavior?>
- **Information flow:** <what did people need to know and not have, or have and not surface?>
- **Has this shape appeared before?:** <link prior incidents with the same structure>

## 🔍 Detection & response
- **How we found out:** <alert / customer / luck>
- **Time-to-detect, and what drove it:**
- **What helped or hindered mitigation:**

## 🎯 Leverage points
<!-- Prefer structural fixes over symptom patches. Rank by leverage, not ease. -->
| Change | Leverage (structure → event) | Owner | Follow-up issue |
|--------|------------------------------|-------|-----------------|
|        |                              |       |                 |

## ✅ What went well
<!-- Name it explicitly — reinforces the behaviors and signals worth keeping. -->

## 🔒 Verification of follow-ups
<!-- Done = the structural change is in place and observable, with an owner. No ownerless TODOs. -->
- [ ] Each leverage-point action has an owner and a tracked issue
- [ ] At least one item changes structure, not just the latest symptom
