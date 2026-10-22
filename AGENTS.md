# Agent Instructions

## Overview

- **Disclosure:** The repository is public and open source.

## Agent Documentation

| Source | Authority and Ownership |
| --- | --- |
| `AGENTS.md` | Defines project instructions, scope, and documentation authority. Applicable project instructions override global defaults. |
| Project-authored skill directories under `.agents/skills/` | Own delegated domain policy, workflows, validation, and reporting exceptions without contradicting applicable `AGENTS.md` instructions. |
| `.agents/PROJECT.md` | Records constraints, durable facts, maintenance decisions, and rationale. It doesn’t override agent instructions. |

## List Entry Format

Within each category under `Packages and Tools`, alphabetize entries using that category’s observed collation. Preserve the bold linked name, spaced em dash, and terminal period. Replace each placeholder in this structure with verified content:

```text
- [**<resource-name>**](<resource-url>) — <description>.
```

Outside `Packages and Tools`, match the existing entry structure and meaningful order under the target heading. `Official Resources` uses plain links without descriptions.

The spaced em dash between a resource name and its description is a structural separator and an explicit exception to the [editorial conventions](#editorial-conventions). Apply those conventions inside descriptions.

In entry descriptions, treat exact identifiers used to install, import, configure, or call software as code tokens, even when they serve as nouns in prose. These include package names, environment identifiers, configuration keys and literal values, and API identifiers. Keep product names, language names, and general technical terms in plain text unless they denote literal identifiers in that context.

## Category Organization

List each resource once, under the category that best fits its primary purpose.

Keep categories under `Packages and Tools` one level deep, without subcategories.

## Editorial Conventions

Load and apply the installed `human-facing-writing` skill when creating or revising text, including drafts delivered in the conversation. This requirement doesn’t apply to agent communication such as resource assessments, explanations, or progress updates.

Its writing and typography rules take precedence over conflicting personal or global policies, regardless of any deference to those policies in the skill itself. The project-specific requirements above remain exceptions.

For installation decisions, see the [managed skills rationale](.agents/PROJECT.md#managed-skills).
