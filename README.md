# claude-draw-io-skill

A Claude Code skill for creating, editing, validating, and exporting structured draw.io diagrams.

## Overview

This skill supports diagram workflows where layout, typography, alignment, and technical accuracy matter. It works with draw.io XML files and helps maintain diagrams used in architecture documentation, engineering specifications, technical presentations, and process explanations.

The workflow favors editing the diagram source and regenerating visual exports instead of manually modifying generated images.

## Supported Workflows

- Create architecture diagrams and infrastructure views.
- Edit existing `.drawio` XML files.
- Build flowcharts, sequence diagrams, and process maps.
- Arrange nodes, containers, labels, and connectors.
- Apply consistent fonts and visual styles.
- Work with cloud architecture icons.
- Convert diagram files to PNG for documents and slides.
- Review layout problems and improve readability.

## Working with Diagram Files

Use `.drawio` as the editable source format. Treat exported PNG files as generated outputs. Make changes in the XML source and regenerate the image after editing.

## Installation

Clone the skill into the Claude Code skills directory:

```bash
git clone https://github.com/Brajesh31/claude-draw-io-skill.git ~/.claude/skills/draw-io
```

Some workflows in this repository use command-line conversion utilities, Python scripts, and pre-commit configuration. Review the available scripts and their dependencies before running them.

## Usage

Invoke the skill for diagram tasks:

```text
/draw-io
```

Provide the diagram file, intended audience, required elements, relationship directions, output format, and any layout constraints.

## Recommended Workflow

1. Inspect the existing diagram and its XML structure.
2. Identify the nodes, containers, labels, and connectors that need changes.
3. Preserve stable element identifiers where possible.
4. Apply consistent typography, spacing, and alignment.
5. Keep connectors behind foreground elements when appropriate.
6. Avoid edge crossings and label collisions.
7. Export the updated diagram.
8. Inspect the exported image at its actual display size.
9. Confirm that the editable source and generated output are consistent.

## Layout and Typography

- Use a consistent font family across the diagram.
- Set the default font at the diagram model level when appropriate.
- Apply explicit font settings to text elements when rendering consistency is important.
- Keep adequate spacing between labels, connectors, and shapes.
- Align related elements using consistent centers or edges.
- Maintain margins inside grouping containers.
- Use a transparent background when the diagram must adapt to different document themes.
- Avoid decorative effects that reduce technical clarity.

## Diagram Organization

For complex systems, split the explanation into focused views:

| Diagram | Main purpose |
|---|---|
| Context | Show users and external systems |
| System architecture | Show major application components |
| Component | Explain internal modules and dependencies |
| Deployment | Show infrastructure and runtime placement |
| Data flow | Show data movement and transformation |
| Sequence | Show time-ordered interactions |

## Export Workflow

The repository includes conversion-related scripts and configuration. Review their expected arguments and environment before execution.

A pre-commit workflow may be used where configured:

```bash
pre-commit run --all-files
```

Use the repository's specific conversion script when a single diagram needs to be exported. Confirm the output dimensions, background, and text readability before publishing it.

## Quality Checklist

- Diagram source remains editable.
- All nodes and connectors are present.
- Labels are readable and do not overlap.
- Arrows communicate direction clearly.
- Group containers have sufficient internal margins.
- Fonts are consistent.
- The background matches the intended use.
- Exported images have been visually inspected.
- Generated files are not mistaken for the editable source.

## Repository Contents

- `SKILL.md`: Main diagram editing instructions.
- `scripts/`: Diagram conversion and icon utility scripts where included.
- `references/`: Layout and diagram resource guidance where included.
- `.pre-commit-config.yaml`: Automated checks and conversion hooks where configured.
- `README.md`: Setup, workflows, and quality checklist.

## Maintenance

Keep source diagrams and generated exports synchronized. When changing conversion scripts or layout conventions, verify the workflow on a small representative diagram before applying it to a large collection.
