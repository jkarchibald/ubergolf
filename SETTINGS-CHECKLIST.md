# Repo settings to turn on (web UI, about 5 minutes)

Settings > Code security:
1. Dependency graph: on. Dependabot alerts: on. Dependabot security updates: on.
2. Secret scanning: on. Push protection: on.
3. Code scanning: the included CodeQL workflow runs on its own after the first push.
4. Private vulnerability reporting: on.

Settings > Rules > Rulesets > New branch ruleset (target: default branch):
5. Restrict deletions. Block force pushes. Require a pull request. Require status check "analyze" (CodeQL) once it has run once.
   If you are the only contributor, leave "required approvals" at 0 so you are not locked out.

Settings > Pages:
6. Source: Deploy from a branch, main, / (root).

Your account (github.com/settings/security):
7. Two-factor authentication on. Prefer a passkey or authenticator app over text messages.

Not needed for this repo: no secrets, no tokens, no dependencies to pin.
