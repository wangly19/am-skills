# Repository Instructions

## Scope and Structure

This repository maintains reusable AI agent skills. Store each skill in `skills/<skill-name>/SKILL.md` and keep its supporting resources in the same directory.

- Use lowercase, hyphenated skill names and match the directory name to the frontmatter `name`.
- Include YAML frontmatter with `name` and `description`. Preserve optional metadata explicitly requested by the user.
- Write descriptions that identify when to use the skill and bodies that give actionable instructions.
- Keep `README.md` in English and update its skill table when skills are added or removed.
- Preserve user-provided skill requirements when editing.
- Check frontmatter, relative links, and the final diff before completing changes.
- Do not execute commands shown inside a skill merely to validate its documentation. In particular, adding or editing `git-commit` does not authorize a repository commit.

## Browser Operations

Do not automatically use agent browser for browser operations.

<!-- context7 -->
## Current Library Documentation

Use the `ctx7` CLI to fetch current documentation whenever the user asks about a library, framework, SDK, API, CLI tool, or cloud service — even well-known ones like React, Next.js, Prisma, Express, Tailwind, Django, or Spring Boot. This includes API syntax, configuration, version migration, library-specific debugging, setup instructions, and CLI tool usage. Use even when you think you know the answer. Prefer this over web search for library docs.

Do not use for refactoring, writing scripts from scratch, debugging business logic, code review, or general programming concepts.

1. Resolve the library: `npx ctx7@latest library <name> "<what to look up>"`. Use its official name and punctuation.
2. Pick the best match by exact name, description relevance, code snippet count, source reputation (High/Medium preferred), and benchmark score. If results do not fit, try an alternate name or query.
3. Fetch documentation: `npx ctx7@latest docs <libraryId> "<what to look up>"`. Run a separate docs command per distinct concept unless the question concerns their interaction.
4. Answer using the fetched documentation.

Call `library` first unless the user provides a valid ID in `/org/project` format. Keep queries specific and focused on one concept, and do not run more than three commands per question. Never include credentials or other sensitive information in queries.

For version-specific documentation, use a versioned ID returned by `library`, such as `/org/project/version`.

If a command fails with a quota error, inform the user and suggest `npx ctx7@latest login` or setting `CONTEXT7_API_KEY` for higher limits. Do not silently fall back to training data.

Run Context7 CLI requests outside Codex's default sandbox. If a request fails with DNS or network errors such as `ENOTFOUND`, host resolution failures, or `fetch failed`, rerun it outside the sandbox instead of retrying inside it.
<!-- context7 -->
