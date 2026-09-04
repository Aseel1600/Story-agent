# COMFYUI WORKFLOW CONTRACT

ComfyUI is the image-generation engine.

The connected AI agent is responsible for operating ComfyUI using whatever ComfyUI tool/interface is available in its environment.

## INPUT PER JOB

Each image job should contain:

- story_id
- asset_id
- page_number if applicable
- prompt
- negative_prompt
- aspect_ratio: 4:5
- width: 3200
- height: 4000
- character references if available
- environment references if available
- required output format

## REQUIRED BEHAVIOR

1. Submit generation.
2. Wait for completion.
3. Retrieve output.
4. Inspect it.
5. Compare with Canon.
6. If inconsistent, regenerate.
7. Save approved image.

## CONSISTENCY PRIORITY

Character identity > scene accuracy > composition > decorative detail.

Do not allow attractive but inconsistent generations to pass.

## OUTPUT

Save approved assets under:

`output/<slug>/03_story_book/images/`

Use stable names:

`cover.png`
`page_01.png`
`page_02.png`
...
`page_32.png`

For derivative products use descriptive stable names.
