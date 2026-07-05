# AGENTS.md

## Repo Shape

- This repo is currently a product requirements document pack for BracketFlow, not an implementation repo.
- There is no app code, package manifest, lockfile, CI, or test/lint/typecheck config; do not invent developer commands.
- Verify changes by rereading the affected Markdown files unless executable tooling is added later.

## Source Order

- Read `01-vision-scope.md` first for product scope, principles, and explicit out-of-scope technical areas.
- Read `03-prd-feature-backlog.md` and `05-acceptance-criteria.md` before changing feature scope or MVP/release boundaries.
- Use `04-user-stories-use-cases.md` for user-flow wording and `02-stakeholder-user-needs.md` for stakeholder needs and pain points.

## Product Constraints

- Product name is BracketFlow: a tournament management platform for Tabletop Wargames.
- Primary users are admins, participants, and spectators. These are the only system roles.
- Admin control is a core principle: admins must be able to manage setup, seeding, participants, scores, corrections, and tournament state.
- The MVP lifecycle is: create tournament -> add/register participants -> seed participants -> start bracket -> report scores -> advance matches -> publish final results.
- MVP formats are single elimination, double elimination, round robin, and Swiss per `03-prd-feature-backlog.md` and `05-acceptance-criteria.md`.
- P2/second-release items include two-stage tournaments, proof/disputes, self-reporting, substitutions, forfeits, templates, and reopen/correction workflows.
- Preserve the numbered acceptance criteria IDs `AC-1` through `AC-51`; reference them when clarifying or adding requirements.
- Treat explicit `TBD` items as unresolved; do not present them as finalized requirements without updating the source doc.
