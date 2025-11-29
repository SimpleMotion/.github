# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Git Commit Guidelines

- Do not include "Co-Authored-By: Claude" or the "Generated with Claude Code" footer in commit messages
- Keep commit messages concise and focused on the changes made

## Repository Overview

This is a SimpleMotion organization-level GitHub repository containing reusable workflows and the organization profile.

## Repository Structure

- `profile/README.md` - Organization profile displayed on GitHub
- `profile/sm-assets/` - Logo and banner assets
- `workflows/` - Reusable workflow templates
  - `ci.yml` - CI workflow (Node.js, Python, Go)
  - `release.yml` - Semantic versioning and changelog generation
  - `security.yml` - CodeQL, dependency review, secret scanning

## Reusable Workflows

All workflows are designed to be called from other repositories using `workflow_call`:

### CI Workflow (`ci.yml`)
- Auto-detects project language (Node.js, Python, Go)
- Configurable via inputs: `node-version`, `python-version`, `go-version`
- Toggle lint/test/build steps with boolean inputs

### Release Workflow (`release.yml`)
- Semantic versioning with automatic version bumping
- Generates changelog from commit history
- Creates GitHub releases

### Security Workflow (`security.yml`)
- CodeQL static analysis (configurable languages)
- Dependency review on PRs (blocks high severity + GPL-3.0/AGPL-3.0)
- TruffleHog secret scanning
