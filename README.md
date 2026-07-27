# sparkstream-legal-public

Public, served copy of SparkStream's user-facing legal documents (Privacy & Data
Policy and Terms of Service). This is the **single source of truth**: both the
desktop app and the marketing website fetch `legal.json` from this repo's raw URL
and render it, so updating this file (and bumping `version` / `effective`) changes
both places at once.

Raw URL: https://raw.githubusercontent.com/Daarko/sparkstream-legal-public/main/legal.json

Only the published legal documents live here. Internal working docs stay in the
private `sparkstream-legal` repo.

## handbook.json — the staff handbook

The SparkStream Staff Handbook, served the same way: the desktop app fetches
`handbook.json` and renders it in the Staff Hub, so it can be corrected without
an app release.

Raw URL: https://raw.githubusercontent.com/Daarko/sparkstream-legal-public/main/handbook.json

**`ackVersion` is an integer and the acknowledgement gate reads it.** Staff must
acknowledge the handbook before they can be certified to work. Bump `ackVersion`
whenever a change is material enough that everyone should read it again; that
re-asks the whole team. Leave it alone for typo fixes. `version` and
`effective.date` are for humans and carry no behaviour.

**This file is WORLD READABLE. It must never contain:**

- Thresholds or counts that decide a moderation outcome. Anything of the form
  "N reports triggers X" tells someone exactly how far they can go.
- How automated content filtering decides anything: rules, term lists, scoring.
- Trust or reputation mechanics.
- Any named individual, or anything identifying a member of staff or a user.
- Anything about a specific case, account, or incident.

Describing that a control *exists* is fine and often good. Describing the number
it turns on is not. `npm run handbook:check` in the Nuclear repo enforces the
mechanical half of this; the judgement half is on whoever edits the file.
