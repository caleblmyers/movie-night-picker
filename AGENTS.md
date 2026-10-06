# Movie Night Picker — agent guide

Movie recommendations, filtered discovery, and personal collections backed by TMDB.

Documentation reviewed 2026-10-05. Implemented Next.js/GraphQL monorepo with deployment configuration. The .NET sibling is a separate rewrite, not this application’s API.

## Start here

- [README.md](README.md) — current setup and project checkpoint

Start with `apps/web` and `apps/api`, and inspect `codegen.yml` before changing the GraphQL contract.

## Repository map

- `apps/web/` — Next.js frontend
- `apps/api/` — GraphQL API and Prisma persistence
- `packages/shared-types/` — generated GraphQL types
- `codegen.yml` — type-generation inputs

## Commands and verification

Run commands from this repository root unless a command specifies another directory. Use the existing lockfile and configured tools.

- `pnpm install` and `pnpm dev` — workspace install and development servers
- `pnpm typecheck` and `pnpm build` — primary validation
- `pnpm lint` — configured lint; API/shared package lint scripts are placeholders
- `pnpm codegen` — regenerate shared GraphQL types
- `pnpm db:migrate` — development database migrations

For documentation-only edits, verify paths, command names, and the diff. For code changes, run the applicable project gates above and report what actually ran; an old checkpoint is not a current test result.

## Project conventions

- Use pnpm and the existing workspace lockfile. Keep GraphQL operations, API schema, and generated shared types synchronized.
- Keep TMDB credentials and database/auth secrets server-side; preserve user ownership of collections, ratings, and reviews.
- Retain TMDB attribution and project licensing.
- No root automated test script exists. Do not report placeholder lint commands as API lint coverage; use typecheck/build and focused behavior verification.

## Scope and handoff

- Preserve existing local changes, environment files, databases, and generated artifacts that the project intentionally tracks.
- Work on the current user request. Reading this file does not start an autonomous loop or authorize publishing, deployment, or unrelated backlog work.
- Keep README setup/status and these instructions aligned when behavior or tooling changes. Record unfinished implementation in the existing project tracker when there is one.
- The owner archived this repository at `archive/movie-night-picker/` on 2026-10-05. Restore it only when requested. Do not move or rename this repository as part of routine development.
