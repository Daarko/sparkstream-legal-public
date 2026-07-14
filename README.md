# sparkstream-legal-public

Public, served copy of SparkStream's user-facing legal documents (Privacy & Data
Policy and Terms of Service). This is the **single source of truth**: both the
desktop app and the marketing website fetch `legal.json` from this repo's raw URL
and render it, so updating this file (and bumping `version` / `effective`) changes
both places at once.

Raw URL: https://raw.githubusercontent.com/Daarko/sparkstream-legal-public/main/legal.json

Only the published legal documents live here. Internal working docs stay in the
private `sparkstream-legal` repo.
