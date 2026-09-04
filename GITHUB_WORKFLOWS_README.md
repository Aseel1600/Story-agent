# Workflow note

The preferred execution model is the connected AI agent itself.

GitHub Actions is intentionally not required for the core pipeline because the user wants the SAME AI agent to orchestrate the prompts and operate ComfyUI.

If later you want unattended server-side execution, a separate workflow can be added.
