# Kimi Development Skills

Kimi Code CLI skills for building production-ready Spring Boot / Java backends — and turning the work into long-form written content.

This repo ports the engineering-focused skills from `your-javaguy-skills` and re-brands them for Kimi Code CLI. The scope is the code-and-ship loop: scaffolding, DevOps, testing, and observability — plus the article skill that drafts in your voice.

---

## The skills

| Skill | What it does |
|-------|--------------|
| `spring-scaffold` | Scaffold a convention-compliant Spring Boot 4 project (pom, feature slices, global exception handling, ProblemDetail, Testcontainers, Dockerfile, GitHub Actions CI, project `AGENTS.md`, README). |
| `devops-scaffold` | Add or update `Dockerfile`, `docker-compose.yml`, and GitHub Actions CI for an existing project. |
| `spring-testing` | Write and repair tests — Testcontainers 2.x setup, integration vs unit routing, and the Boot 4 test API (`@MockitoBean`, `MockMvcTester`, `RestTestClient`). |
| `otel-setup` | Wire OpenTelemetry end to end — OTLP export, the Logback appender Boot does not ship, a local Grafana LGTM backend, and a runbook that proves all three signals land. |

### Content

| Skill | What it does |
|-------|--------------|
| `article` | Write a long-form technical article in your voice — Substack, dev.to, Medium, or Hashnode — grounded in real work, drafted as a plain-text `.txt` file for review. |

---

## Install

Kimi Code CLI discovers skills in three ways: as a plugin, project-locally from the current working
directory, or globally from the user skills directory (`~/.agents/skills/`).

### Option A — Plugin install (recommended)

If Kimi Code CLI supports plugin installation from a local path or a repository, install the plugin
using the manifest in `.kimi-plugin/plugin.json`. The exact command depends on the Kimi Code CLI
version, but is typically something like:

```bash
kimi plugin add /path/to/development-skills
# or, once published:
kimi plugin add Dancan254/development-skills
```

The manifest declares `"skills": "./skills/"`, so all skills are registered automatically.

### Option B — Project-local (try it out)

```bash
git clone https://github.com/Dancan254/development-skills.git
cd development-skills
```

Then just start talking to Kimi Code CLI from inside the repo. The skills in `skills/<name>/SKILL.md`
are loaded automatically.

### Option C — User/global (always available)

Make the skills available from any directory:

```bash
ln -s /path/to/development-skills ~/.agents/skills/development-skills
```

Or copy the repo there if you don't want a symlink:

```bash
cp -r /path/to/development-skills ~/.agents/skills/development-skills
```

Restart or reload Kimi Code CLI if it was already running. Skills are read from `SKILL.md` files
inside each `skills/<name>/` directory.

---

## Setup

### For the `article` skill

The voice profile ships as a template. Before your first article, fill in the placeholders in
`skills/article/references/voice-profile.md`:

- `[Your Name]`
- `[Your Publication / Platform]`
- `[Your tagline]`
- Any metaphors or humor examples you want to replace with your own

Once those placeholders are replaced, every article draft will sound like you instead of generic
"engaging blog" prose.

---

## How to use

Each skill is a directory under `skills/<name>/` containing a `SKILL.md` file and optional `references/`.

Kimi Code CLI loads skills automatically when the working directory is this repo (or when the skill
pack is linked under `~/.agents/skills/`). Describe what you want in plain language; the skill
description acts as the trigger. Example:

```
Scaffold a new Spring Boot project called order-service that manages Orders and Customers.
```

The matching skill (`spring-scaffold`) will run and generate the project.

You rarely invoke a skill by name; just describe the outcome you want.

---

## Layout

```
.
├── README.md
├── AGENTS.md
└── skills/
    ├── spring-scaffold/
    │   ├── SKILL.md
    │   └── references/
    │       └── pagination.md
    ├── devops-scaffold/
    │   ├── SKILL.md
    │   └── references/
    │       └── parallel-agent-runs.md
    ├── spring-testing/
    │   ├── SKILL.md
    │   └── references/
    │       ├── containers.md
    │       └── conventions.md
    └── otel-setup/
    │   ├── SKILL.md
    │   └── references/
    │       └── otel-reference.md
    └── article/
        ├── SKILL.md
        └── references/
            ├── article-craft.md
            └── voice-profile.md
```

---

## Version policy

Skills are pinned to **Spring Boot 4.1.1** by default. Other pins (Temurin JDK, PostgreSQL, Grafana LGTM, Testcontainers, GitHub Actions) are current as of the last sweep. Each skill includes the exact `curl` command to re-verify a pin before writing it, so the scaffold never ships a stale default.

Do not override `testcontainers.version` or `opentelemetry.version` by hand — the Spring Boot BOM owns them. If a newer release exists, that is a Boot upgrade, not a property change.

---

## License

MIT
