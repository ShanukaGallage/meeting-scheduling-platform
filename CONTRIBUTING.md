# Contributing to MeetSchedule

Thanks for being part of the team! This guide covers everything you need to contribute effectively — branching strategy, commit style, pull requests, and code standards.

---

## 📋 Table of Contents

- [Getting Started](#getting-started)
- [Branching Strategy](#branching-strategy)
- [Commit Messages](#commit-messages)
- [Pull Requests](#pull-requests)
- [Code Standards](#code-standards)
- [Adding a New Team Member](#adding-a-new-team-member)

---

## Getting Started

1. Make sure you've completed the local setup in [README.md](./README.md)
2. Ask the repo admin to add you as a collaborator on GitHub
3. Never push directly to `main` — always work on a branch and open a PR

---

## Branching Strategy

We use a simple feature-branch workflow.

### Branch naming

```
<type>/<short-description>
```

| Type | When to use |
|---|---|
| `feat/` | A new feature |
| `fix/` | A bug fix |
| `docs/` | Documentation only |
| `refactor/` | Code change that doesn't fix a bug or add a feature |
| `test/` | Adding or fixing tests |
| `chore/` | Dependency updates, config changes, CI tweaks |

**Examples:**
```
feat/booking-page
fix/timezone-detection
docs/setup-guide
chore/update-prisma
```

### Rules

- Branch off from `main`
- Keep branches short-lived — open a PR as soon as the feature is working
- Delete your branch after it's merged

---

## Commit Messages

We follow the [Conventional Commits](https://www.conventionalcommits.org/) format:

```
<type>(<scope>): <short description>

[optional body]

[optional footer]
```

**Examples:**

```
feat(booking): add shareable booking link generation
fix(auth): resolve Google OAuth redirect loop
docs(readme): update local setup instructions
chore(deps): upgrade prisma to 5.12
```

### Rules

- Use the **imperative mood** in the description: "add feature" not "added feature"
- Keep the first line under **72 characters**
- Reference a Jira ticket in the footer if applicable: `Closes MICUOK-42`

---

## Pull Requests

### Before opening a PR

- [ ] Your branch is up to date with `main`
- [ ] All tests pass locally (`pnpm test`)
- [ ] TypeScript compiles without errors (`pnpm typecheck`)
- [ ] Linting passes (`pnpm lint`)
- [ ] You've tested your changes manually

### PR title

Use the same format as commit messages:
```
feat(booking): add shareable booking link generation
```

### PR description

Fill in the PR template (created automatically when you open a PR). At minimum include:
- What this PR does
- How to test it
- Screenshots if it's a UI change
- Link to the Jira ticket

### Review process

- Every PR requires **at least 1 review** before merging
- The author should **not** merge their own PR
- Reviewers: leave constructive comments, approve when satisfied
- After approval: the **author merges** using "Squash and merge"

---

## Code Standards

### TypeScript

- Strict mode is enabled — no `any` types without a comment explaining why
- Export types from `packages/types` if they're shared between apps

### Styling

- Use Tailwind utility classes only — no custom CSS unless absolutely necessary
- Follow the existing component patterns in `packages/ui`

### API

- All endpoints must be typed end-to-end (Prisma → Hono → Frontend)
- Return consistent error shapes: `{ error: string, code: string }`
- Never expose raw database errors to the client

### Database

- All schema changes go through Prisma migrations (`pnpm db:migrate`)
- Never edit the database directly in production

### Testing

- Write a unit test for every new utility function
- Write an integration test for every new API endpoint
- E2E tests for any complete user flow (booking, polling)

---

## Adding a New Team Member

1. Go to the repo on GitHub → **Settings → Collaborators → Add people**
2. Search by their GitHub username and send an invite
3. Set their role to **Write** (not Admin)
4. Share this CONTRIBUTING.md with them and ask them to read it before their first commit
5. Add them to the MICUOK Jira project and Confluence space
