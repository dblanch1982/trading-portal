---
name: github-automation
description: Use when creating, updating, or troubleshooting GitHub Actions automation for the trading-portal Angular project, including CI checks and release workflows.
---

# GitHub automation for trading-portal

Use this skill when a task involves automating this repository through GitHub Actions. Keep workflows in `.github/workflows/` and tailor them to the Angular application in `src/`.

## Project commands

- Install dependencies with `npm ci` when a `package-lock.json` is present; otherwise use `npm install` and add the resulting lockfile if dependency setup is part of the task.
- Build the application with `npm run build`.
- Run tests with `npm test` when the repository contains applicable tests.

Check `package.json` before relying on a script or adding a new one. Do not silently skip a required check when its script or dependencies are missing; report the gap or add the smallest appropriate setup.

## Workflow guidelines

1. Inspect the existing workflows, package scripts, lockfile, and Angular configuration before editing.
2. Make workflows event-scoped to the request, use explicit job and step names, and grant only the minimum required `permissions`.
3. For CI, prefer a stable Node.js version supported by the project, enable npm caching when dependencies are installed, use the lockfile with `npm ci`, and run the relevant checks.
4. Keep credentials in GitHub Actions secrets. Never add tokens, passwords, or other credentials to workflow files, logs, or repository code.
5. Do not add deployment, publishing, release, or write-permission steps unless explicitly requested. Do not run external scripts or third-party actions without checking their source and pinning policy.
6. Validate workflow YAML and run the same package scripts locally when available. Clearly report any check that could not be run.

## Completion

Summarize which automation was added or changed, its trigger and checks, and any required repository settings or secrets. Do not claim a workflow was executed unless its run result is available.
