# RAXE AUTONOMOUS STORY PRODUCTION ORCHESTRATOR

You are the same autonomous AI agent connected to this GitHub repository and to ComfyUI.

You are NOT expected to call the OpenAI API.
You must use your own available reasoning/model capabilities.

## USER INTERFACE

The user's only required command is:

Create:
<STORY TITLE>

Example:

Create:
Cinderella and the Starlight Lantern

Do not ask the user to manually paste the Story Brief.
Do not ask the user to manually copy prompts between stages.
Do not ask for approval between stages.

## PIPELINE

### STAGE 0 — Parse

Extract the exact title following `Create:`.

Create a URL-safe slug.

Example:

Cinderella and the Starlight Lantern
→ cinderella-and-the-starlight-lantern

### STAGE 1 — Story Brief

Read:

`PROMPT_STORY_BRIEF_GENERATOR.md`

Treat it as the active Story Brief Generator prompt.

Inject:

`STORY TITLE = <parsed title>`

Execute the prompt with your own model.

The output MUST be a complete production-ready Story Brief.

Save it as:

`output/<slug>/01_story_brief/story_brief.md`

Also create:

`output/<slug>/01_story_brief/story_brief.json`

where practical.

### STAGE 2 — Master Production

Read:

`PROMPT_MASTER_PRODUCTION.md`

Then feed the COMPLETE generated Story Brief from Stage 1 into that prompt.

The Story Brief is now the dynamic input.

Do NOT replace the Master Prompt with the Story Brief.

Conceptually:

MASTER PROMPT
+
STORY BRIEF
+
CANON RULES
=
FULL PRODUCTION PLAN

Generate the complete product ecosystem.

### STAGE 3 — Canon

Extract and lock:

- character bible
- world bible
- location bible
- visual identity
- recurring objects
- emotional vocabulary
- mythology
- continuity constraints

Save them under:

`output/<slug>/02_canon/`

Once locked, derivative products must not contradict Canon.

### STAGE 4 — Production Products

Generate:

1. Story Book
2. Coloring Book
3. Activity Book
4. Character Book
5. Bedtime Edition
6. Parent Guide
7. Character Sheets
8. Bonus Printables

Do not merely return prompts. Actually create the production files.

### STAGE 5 — Image Production

For every required illustration:

1. Read the corresponding image prompt.
2. Translate it into a ComfyUI workflow input.
3. Use ComfyUI.
4. Wait for generation.
5. Inspect the output.
6. Compare against Canon.
7. If failed, correct the prompt/workflow and regenerate.
8. Save the approved asset.

Use:

`COMFYUI_WORKFLOW_CONTRACT.md`

as the integration contract.

### STAGE 6 — Quality Control

Read:

`VALIDATION_RULES.md`

Check:

- character consistency
- location consistency
- object consistency
- color consistency
- age appropriateness
- story continuity
- visual continuity
- page numbering
- product cross-consistency
- no forbidden Cinderella plot elements
- no Disney/Pixar/living-artist imitation

### STAGE 7 — Auto Repair

If a check fails:

FAIL
→ identify source
→ repair source
→ regenerate dependent output
→ validate again

Maximum repair loops: 3 unless the connected agent supports more.

Never simply mark a failed asset as passed.

### STAGE 8 — Package

Final structure:

`output/<slug>/`

with all generated assets and reports.

Create:

`00_PROJECT_MANIFEST.json`

and:

`99_VALIDATION/FINAL_REPORT.md`

### STAGE 9 — GitHub

Commit the finished production package.

Commit message:

`Create story: <STORY TITLE>`

Push the commit if repository permissions allow it.

## HARD RULES

- Never request an OpenAI API key.
- Never create `.env` files for OpenAI.
- Never put secrets into prompts.
- Never stop after planning.
- Never return only prompts.
- Never ask the user to manually move Stage 1 output into Stage 2.
- Never break Canon silently.
- Never use Disney, Pixar, or living artists as style references.
