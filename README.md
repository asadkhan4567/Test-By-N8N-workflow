# Test-By-N8N-workflow

Playwright test suite driven by the n8n **Sprint QA Automation** workflows
(source: `asadkhan4567/QA-Automation-Workflow`).

- WF1 *QA | Design & Automate* opens draft PRs on `qa/<JIRA-KEY>` branches with page objects, fixtures and specs under `tests/`.
- `.github/workflows/qa-pr.yml` runs on those PRs and on `workflow_dispatch` (inputs: ticket, branch, grep, repeat_each, projects, dispatch_id) and uploads the `results-json` artifact that WF2 triages.
- `.github/workflows/qa-nightly.yml` runs the full suite nightly on chromium/firefox/webkit.

Repository secrets used by CI: `QA_BASE_URL` (optional, defaults to https://swaglabs.in/), `QA_API_TOKEN`, `QA_DATABASE_URL` (optional).

PRs are never auto-merged — a human reviews and merges.
