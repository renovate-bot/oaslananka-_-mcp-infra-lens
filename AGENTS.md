# AGENTS.md

## This repo is source and CI/CD execution

Source of truth: oaslananka/mcp-infra-lens
GitHub Actions run in this repository.

## Control-plane

oaslananka-ops/_ops

## Before any PR work

Run diagnostics:

```sh
gh workflow run .github/workflows/agent-pr-diagnostics.yml \
  --repo oaslananka-ops/_ops --ref main \
  -f target_owner=oaslananka \
  -f target_repo=mcp-infra-lens \
  -f pr_number={PR_NUMBER}
```

## Before any release

```sh
gh workflow run .github/workflows/repo-release-plan.yml \
  --repo oaslananka-ops/_ops --ref main \
  -f target_owner=oaslananka \
  -f target_repo=mcp-infra-lens
```

## Merge rule

Squash only. Never merge without clean diagnostics.

## Operating contract

https://github.com/oaslananka-ops/_ops/blob/main/docs/agent-operating-contract.md
https://github.com/oaslananka-ops/_ops/blob/main/docs/architecture.md