<!-- LEGEND: ✍️ = author action before requesting review · 👀 = reviewer action during review.
     These record work done to build shared understanding, not guarantees — they are not used to assign fault. -->

## ✍️ Risk Tier
<!-- Author picks one. Drives reviewer attention and may affect required approvals. -->
- [ ] 🟢 Low — additive, flagged, docs-only, or test-only
- [ ] 🟡 Medium — behavioral change, no data/schema/security risk
- [ ] 🔴 High — schema/migration, auth, security, billing, money, or data backfill

## ✍️ If 🟡 or 🔴, fill this:
- **Worst case:**
- **How we'd detect issues after merge/release:** <metric / alert / log / user report>
- **Rollback plan:**
- **Migration safety:** <N/A? online? backfill batched? reversible?>

## ✍️ Summary
<!-- Author: 2–4 sentences. What changed and why. -->
Closes #

## Checks
- [ ] ✍️ CI green, or reason noted
- [ ] ✍️ New behavior covered by tests, or reason noted
- [ ] ✍️ No unrelated changes in this diff
- [ ] 👀 Reviewer: assessed the risk tier; raised it with the author only if it seems wrong
- [ ] 👀 Reviewer: assessed the rollback/detection plan (🟡/🔴 only)
