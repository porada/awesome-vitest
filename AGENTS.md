# Agent Instructions

## List Entry Format

Within each category under `Packages and Tools`, keep entries alphabetized using that category’s observed collation, and preserve the bold linked name, spaced em dash, and terminal period. Use this structure, replacing each placeholder with verified content:

```text
- [**<resource-name>**](<resource-url>) — <description>.
```

Outside `Packages and Tools`, match the existing format and meaningful order under the target heading. `Official Resources` uses plain links without descriptions.

The spaced em dash between a package name and its description is a structural separator, not pause punctuation. It is the only exception to the no-spaces rule below. Apply the prose punctuation rules inside descriptions.

In entry descriptions, exact identifiers used to install, import, configure, or call software qualify as code tokens. This includes package names, environment identifiers, configuration keys and literal values, and API identifiers, even when used as nouns in prose. Product names, language names, and general technical terms remain plain text unless they denote literal identifiers in that context.

## Category Organization

List each resource once, under the category that best fits its primary purpose. `/add-entry` must use existing categories and must not suggest new ones or change the hierarchy. If none fits, report the placement issue and defer the addition.

Keep categories under `Packages and Tools` one level deep, without subcategories.

## Writing

- **Typography:** Use typographic “quotation marks” and apostrophes in prose. Preserve exact punctuation where literal syntax requires it.
- **Oxford comma:** In a list of three or more items, place a comma before the final conjunction.
- **Semicolons:** Never introduce semicolons in prose or human-facing technical copy. Preserve a supplied semicolon only when the user explicitly wants it retained.
- **Pause punctuation:** Limit dashes and other punctuation used to create a pause. Use a dash only when its additional pause or emphasis materially improves the text. Never surround em dashes with spaces.
- **Hyphenation:** These defaults apply to modifiers before nouns in all human-facing prose, including GitHub collaboration. Choices between hyphenated and closed spellings remain outside scope, as do predicative uses and verbs.
    - **Noun phrases:** Keep normally open noun phrases open when they modify another noun. Their position before a noun is not, by itself, a reason to add a hyphen. Write `file pattern imports`, not `file-pattern imports`. Use a hyphen only to prevent a specific, plausible misreading.
    - **Adverb modifiers:** Do not join `already` or an adverb ending in `-ly` to the adjective or participle it modifies with a hyphen. Write `already published articles`, `highly readable prose`, and `widely quoted passages`.
    - **Other compound adjectives:** Otherwise retain conventional hyphenation, as in `best-known authors`, `fast-moving narratives`, `long-running columns`, `longest-running series`, and `well-defined terms`.
- **Code tokens:** Wrap identifiers, paths, commands, and quoted code tokens in backticks.
