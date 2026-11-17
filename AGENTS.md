# AGENTS.md

This repository provides `ptah.run/testkit`, reusable helpers for database
tests. The [README](README.md) describes the public helpers;
[go.mod](go.mod) records the dependency versions and the
[Go workflow](.github/workflows/go.yml) defines build and test checks.

## Pull request descriptions

### Purpose and scope

- Read and follow `.github/pull_request_template.md`, including when
  creating or updating a PR through a CLI or API. Keep its headings and
  remove drafting comments and unused optional content.
- Write in plain American English and follow the repository's title
  convention. The title and first paragraph must make the purpose clear
  to a reviewer who knows the project but not the investigation. Define
  uncommon terms before using them. Do not add tool signatures or
  generated-with footers.
- Establish intent from the request, issue, discussion, and supporting
  evidence. Do not invent user impact, urgency, performance gains, or
  security benefits. Ask for clarification when missing information
  materially changes the goal, scope, acceptable risk, or completion
  criteria.
- Explain the problem or need and the resulting behavior. For a bug fix,
  explain the established cause. Distinguish observations, conclusions
  drawn from code, and hypotheses.
- Describe meaningful limitations and non-obvious decisions. Include
  implementation details when they help assess correctness, risk, or use.
  Avoid file inventories, commit histories, and repeated summaries.
- Keep the essential explanation in the PR. Link issues that define its
  scope, required companion changes, and relevant remaining work.
  Use closing keywords only when the PR fully resolves an issue.

### Evidence and maintenance

- Report observed validation results and important coverage gaps.
  Explain what each significant check establishes. Do not present lint,
  compilation, skipped checks, or planned work as proof of behavior they
  do not verify.
- State the engines, versions, platforms, or component combinations
  actually exercised when they affect the claim. Provide manual steps
  only where they add useful verification.
- Before publishing, inspect the complete diff from the actual base
  branch to the current head. When updating an existing PR, read its
  current title and description first.
- After substantive changes, revise the description for the complete
  current PR. Update behavior, scope, risks, dependencies, and validation
  claims; replace stale text instead of appending a development diary.
- Keep the description proportional to the change. Put essential results,
  material risks, and remaining uncertainty in the main text. Link or
  collapse lengthy supporting evidence.
- Follow all repository-specific testing, documentation, safety, and
  compatibility requirements alongside this description standard.

The shared wording of this section and the PR template is maintained in
[`stokaro/ptah`](https://github.com/stokaro/ptah). Keep copies aligned across
Ptah repositories; put repository-specific additions in a separate section.

## Testkit-specific PR details

- For a public helper change, explain its effect on consuming tests, including
  relevant setup, isolation, cleanup, reuse, and error behavior. Identify
  required changes in Ptah or other consumers when they affect adoption.
- State the Ptah dependency and database environments actually exercised
  when they affect the claim. Distinguish SQLite checks from tests that need
  container-backed engines, and report any skipped or unavailable checks.
- For a changed fixture or test helper, explain which consumer behavior the
  evidence covers. Compilation alone does not establish database lifecycle
  or migration behavior; identify the relevant execution and observed result.
- Use the existing [Go workflow](.github/workflows/go.yml) for applicable
  build, vet, test, and module checks. Record a temporary local replacement
  as a validation limitation when assessing the published dependency.
