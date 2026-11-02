# am-skills

A collection of reusable skills for AI coding agents. Each skill contains a `SKILL.md` file with metadata, activation criteria, and task instructions.

## Available Skills

| Skill | Description |
| --- | --- |
| [am-feature](skills/am-feature/SKILL.md) | Clarify feature requirements through a focused text conversation in English and write an English specification to `docs/feature/<topic>.md` without implementing it. |
| [git-commit](skills/git-commit/SKILL.md) | Analyze changes, stage related files, and create emoji-prefixed Conventional Commits. |

## Repository Structure

```text
am-skills/
├── AGENTS.md
├── README.md
└── skills/
    ├── am-feature/
    │   └── SKILL.md
    └── git-commit/
        └── SKILL.md
```

## Usage

Copy the desired skill directory from `skills/` into the skills directory supported by your agent. Consult your agent's documentation for its installation location and supported metadata.

For example, after installing `git-commit`, ask your agent:

```text
Commit the current changes.
```

The skill instructs the agent to inspect the diff, group related changes, and generate a message such as:

```text
✨ feat(auth): add refresh token rotation
```

The `/commit` phrase is a trigger described by this skill; whether it is available as a slash command depends on the host agent.

## Contributing

Create each skill in `skills/<skill-name>/SKILL.md`, using a lowercase, hyphenated directory name that matches its frontmatter `name`. Include a clear `description` explaining when the skill should activate, followed by actionable instructions and relevant examples.

Keep supporting scripts, references, and assets inside the skill directory when needed. Update the skill table above when adding or removing skills. See [AGENTS.md](AGENTS.md) for repository guidance.
