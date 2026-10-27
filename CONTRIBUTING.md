# Contributing Guidelines

Submissions are welcome!

## Quick Start

Use the included [agent skill](.agents/skills/add-entry/SKILL.md) to assess a resource and add it to the list if it’s a good fit. Pass this prompt to your agent:

```text
Resource: <resource-url>
Repository: https://github.com/porada/awesome-vitest

1. Set up the repository.
2. Follow the instructions in `.agents/skills/add-entry/SKILL.md`.
3. Push any commits to my fork, creating one if needed.
```

If you’ve already cloned the repository, use the skill directly:

```text
/add-entry <resource-url>
```

## Submission Standards

- **Include one resource per submission.**

    Submit a tool you’ve actually used and can vouch for.

- **Choose Vitest-specific resources.**

    Jest packages compatible with Vitest don’t qualify.

- **Add your entry in alphabetical order.**

    Place it within the relevant section, regardless of submission date.

- **Keep your description concise.**

    Vitest support is already implied. Avoid phrases such as `Vitest plugin`, `Vitest tests`, or `for Vitest`.

- **Allow maintainer edits.**

    Keep `Allow edits by maintainers` enabled on your pull request. This won’t affect your contribution credit.
