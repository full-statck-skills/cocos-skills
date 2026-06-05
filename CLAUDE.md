# CLAUDE.md — cocos-skills

Part of the [Full Stack Skills](https://github.com/partme-ai/full-stack-skills) ecosystem maintained by PartMe.AI.
This repo publishes Agent Skills installable via `npx skills add full-statck-skills/cocos-skills`.

## Skills (1)

| Skill | Description |
|-------|-------------|
| `cocos2d-x` | Cocos2d-x v4 game engine — scene graph, sprites, actions, animations, physics, shaders, platform deployment |

## Directory Structure

```
skills/
  cocos2d-x/               # one directory per skill
    SKILL.md               # required: YAML frontmatter + markdown body
    LICENSE.txt            # skill-specific license
    examples/              # reference docs loaded on-demand by the agent
      getting-started/     # about-engine, installation, quick-start
      core/                # node-scene, sprite, texture, animation, action,
                           #   label, scene, input, event
    api/                   # API reference docs (empty by convention, pending fill)
    templates/             # project-structure, cmake-config
```

- Each skill is a self-contained directory with a `SKILL.md` entry point.
- `SKILL.md` lists when-to-use triggers, maps topics to example files, and gives coding conventions.
- Example files are Chinese-language C++ guides with syntax, examples, and links to official docs at docs.cocos.com.

## SKILL.md Authoring Conventions

- **YAML frontmatter** — `name`, `description` (1-2 sentences, used in catalog), `license`
- **`## When to use this skill`** — trigger phrases in English
- **`## How to use this skill`** — numbered workflow: identify topic → load example → generate code
- **`### Doc mapping`** — 1:1 links to official documentation
- **`## Core Concepts`** — high-level summaries of Node, Action, Scene, Input systems
- **`## Keywords`** — comma-separated, includes both English and Chinese terms
- Example files follow a fixed pattern: official doc link → overview → syntax → examples → reference

## Key Constraints

- Skill targets **Cocos2d-x v4**, C++ only
- **CMake** is the build system; OpenGL-style coordinates (origin bottom-left)
- Most operations must run on the **main thread**; reference counting for memory management
- This repo is bilingual (English README + zh-CN README), example files are in Chinese

## Key Files

| File | Purpose |
|------|---------|
| `README.md` / `README.zh-CN.md` | Public-facing readme with install instructions and skill table |
| `skills/<name>/SKILL.md` | Skill entry point loaded by agents |
| `skills/<name>/examples/**/*.md` | Topic-specific reference docs |
| `LICENSE` | Apache 2.0 |
