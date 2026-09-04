# RAXE Children's Story Production Agent — NO API

This repository is designed for an autonomous AI agent connected to GitHub and ComfyUI.

## ONLY USER COMMAND

```text
Create:
<STORY TITLE>
```

Example:

```text
Create:
Cinderella and the Starlight Lantern
```

## AUTONOMOUS PIPELINE

The connected AI agent must:

1. Read `AGENT_ORCHESTRATOR.md`.
2. Parse the title after `Create:`.
3. Read `PROMPT_STORY_BRIEF_GENERATOR.md`.
4. Inject the title into the fixed Story Brief Generator.
5. Generate the complete Story Brief using its own model/reasoning.
6. Read `PROMPT_MASTER_PRODUCTION.md`.
7. Feed the generated Story Brief directly into the Master Production Prompt.
8. Read the ComfyUI and validation contracts.
9. Execute the complete production.
10. Generate images through the connected ComfyUI environment.
11. Inspect, correct, and regenerate failed assets.
12. Validate story, character, world, visual, and product consistency.
13. Package the final story universe/products.
14. Save and commit production outputs to GitHub.

## NO API ARCHITECTURE

- No OpenAI API.
- No `OPENAI_API_KEY`.
- No external LLM API.
- The connected AI agent is the reasoning/execution engine.
- GitHub is the source of truth and persistent storage.
- ComfyUI is the image-generation engine.
- No manual Story Brief copy/paste.
- Do not stop at planning or return only prompts.

## ROOT-UPLOAD DESIGN

All operational files are intentionally available in the repository root. You can use GitHub's **Upload files** flow and upload the complete set together without manually creating project folders.

Key files:

- `AGENT_ORCHESTRATOR.md`
- `PROMPT_STORY_BRIEF_GENERATOR.md`
- `PROMPT_MASTER_PRODUCTION.md`
- `COMFYUI_WORKFLOW_CONTRACT.md`
- `VALIDATION_RULES.md`
- `PRODUCTION_CONFIG.json`
- `GITHUB_WORKFLOWS_README.md`

After upload and agent connection, the intended user interaction is simply:

`Create: <story title>`
