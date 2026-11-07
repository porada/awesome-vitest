# Add Entry

## Resolve Scope

A candidate link or name requests an inclusion assessment and, when suitable, a draft entry. Apply the same inclusion standard to someone’s own package and to resources they don’t maintain.

For an explicit wording-only request, consult the relevant parts of Awesome Vitest and continue at [Prepare Entry](#prepare-entry) without reopening a settled inclusion decision. If editing reveals a potential suitability problem, check it against [the inclusion criteria](resource-assessment.md#assess-resource-fit) and disclose a concrete problem rather than silently turning the request into a broader investigation. When wording is explicitly requested after a negative assessment, provide it without implying that the recommendation changed.

Process every supplied item independently, preserving input order and reusing shared evidence. Limit additional investigation to what resolves those items. Don’t discover unrelated resources or audit the inventory.

Default to read-only assessment and draft output. Invocation alone doesn’t authorize repository edits, commits, submissions, or publication. Follow separately requested changes within their explicit scope and applicable approval boundaries. A recommendation isn’t maintainer acceptance, and approval of wording isn’t approval to include a resource.

## Establish List Context

Use `README.md` and `CONTRIBUTING.md` at the root of this Awesome Vitest checkout.

Read the contribution guidelines as the list’s submission requirements. For an inclusion assessment, read the complete entry inventory to check existing identities and links, then examine entries under relevant headings for overlap, placement, and editorial context. For wording-only work, use the supplied text and entries under the target heading. Treat existing entries as context, not proof that every historical inclusion or wording choice remains sound.

If a required source can’t be read, state the limitation and defer conclusions that depend on it. Wording-only work may continue from supplied text. Don’t claim to have checked the current list or contribution requirements when that source was unavailable.

Keep technical suitability separate from submission readiness. Apply the current contribution requirements when preparing someone to submit, including any firsthand use requirement. Source inspection doesn’t establish personal use, execution of tests, or endorsement on the contributor’s behalf.

## Assess Resource Fit

For an inclusion assessment, follow [Resource Assessment](resource-assessment.md) to assess fit and select a recommendation. Continue at [Prepare Entry](#prepare-entry) if you’ll draft or edit an entry, regardless of the recommendation. Otherwise, continue at [Deliver Results](#deliver-results). Wording-only work bypasses this assessment.

## Prepare Entry

Before drafting or editing an entry, including wording-only work, read and apply the [project entry requirements](../../../../AGENTS.md).

### Load Writing Guidance

Load `human-facing-writing` through the client when available, or read `.agents/skills/human-facing-writing/SKILL.md` directly.

If neither source is available, use the repository’s declared dependency setup as needed, then run `pnpm run postinstall` if the installed entrypoint is still absent. Run setup only when the task authorizes it and applicable approval and access requirements are satisfied. If setup needs approval, can’t be completed, or leaves the entrypoint unavailable, report what’s needed along with any completed assessment results, apply the title rules under [Deliver Results](#deliver-results), and stop before drafting or editing entries. After setup, read the installed entrypoint before continuing.

### Draft Entry

Apply description guidance only when entries under the target heading use descriptions.

- **Identity and destination:** Use the verified resource name. For repository-hosted GitHub Actions, use the verified `uses` identifier without the `@<ref>` suffix as the resource name. Preserve the owner, repository, and any action subdirectory rather than using only the repository basename or the action’s display name. For a package supplied through npm or another non-GitHub URL, try to locate its GitHub repository. Prefer a useful GitHub destination over npm. In a monorepo, inspect the relevant package directory and use it when it has a substantive README and makes a useful landing page. Otherwise use the repository root rather than an undocumented subdirectory. Canonical documentation links are also valid destinations for package entries.
- **Capability and distinction:** Describe what the resource helps readers do. Preserve a material distinction from nearby alternatives without listing incidental implementation details or letting one minor feature misrepresent its breadth. When available evidence doesn’t establish whether a feature is minor, consult the resource’s documented purpose and usage examples before omitting it, including during wording-only work. Emphasize benchmarks only when they are a highlight feature.
- **Wording and consistency:** Prefer shorter, concrete descriptions that preserve the resource’s purpose and material distinctions. Match useful nearby patterns and deliberate parallel wording while retaining differences. Sentence fragments and verb-led descriptions can both fit. Avoid repeating context from Awesome Vitest or the target heading when it adds no information, but don’t turn words such as `Dedicated`, `Vitest`, or `environment` into universal requirements or prohibitions.

If preserving a user’s wording choice conflicts with the project entry requirements, disclose the conflict. Don’t treat a source description as approved entry copy. A user’s objection establishes a problem with the rejected wording, not acceptance of an agent’s replacement. Don’t guess the referent of an ambiguous selection when it changes the resulting entry.

### Choose Placement

Follow the [project category rules](../../../../AGENTS.md#category-organization) and use existing categories. If none fits, report the placement issue and defer the addition until placement is resolved.

When a supplied resource exposes a placement issue, use [maintainer verification](#verify-maintainer-account) to determine whether category proposals are available. In the standard workflow, don’t suggest or make category changes. When the maintainer workflow is enabled, suggest a new category or a relevant rename, split, merge, or reassignment of existing entries when useful. Keep proposals tied to that resource and within the project category rules rather than auditing the inventory.

For maintainer proposals, explain the placement problem and proposed change. Keep this skill’s category work limited to proposals. Applying and committing a proposal requires separately approved work through the applicable change and commit workflows. If an entry depends on it, defer the addition until the category change is committed. Keep category changes out of the addition commit.

## Deliver Results

For each assessed resource, identify it, state its recommendation, and provide a concise rationale with the decisive source links. Follow the selected outcome’s output contract rather than producing a fixed audit report. Call out material uncertainty or unmet submission requirements.

Present each proposed entry as a rendered Markdown list item in a blockquote. Use a fenced code block for an entry only when the user explicitly requests raw Markdown. For wording-only work, return the proposed item and any material caveat without fabricating an inclusion verdict.

Before delivery, check that the name, destination, and any description match the evidence, that duplication and overlap are reflected in the recommendation, that the placement and Markdown fit the current list, and that the entry follows the [project entry requirements](../../../../AGENTS.md). For inclusion recommendations, also verify the evidence line required by [Select Recommendation](resource-assessment.md#select-recommendation).

After selecting the final assessment recommendation, update the assessing thread’s own title if the client supports renaming it. Remove any existing leading `✓ ` or `× ` markers, then prepend a marker only for a single-entry assessment: `✓ ` (`U+2713` followed by a space) for Recommend inclusion or `× ` (`U+00D7` followed by a space) for Do not recommend inclusion. Use no marker for Defer recommendation. Apply these rules again when the candidate count or recommendation changes.

Count distinct candidates across messages in the thread, restarting after an entry commit. A count of one defines a single-entry assessment, and reassessing the same candidate doesn’t increase it. When a new single-entry assessment follows an entry commit, replace the previous candidate’s name in the title with the current candidate’s name if needed. Preserve all other title text.

Leave the title unchanged for wording-only work. Never rename another thread. If renaming isn’t supported, skip it without changing the assessment.

### Add Approved Entries

When an assessment recommends inclusion or the user explicitly chooses inclusion, use [maintainer verification](#verify-maintainer-account) to select the workflow before offering actions. Don’t offer additions for wording-only requests.

If the maintainer workflow is enabled and the request isn’t explicitly limited to assessment, follow the [maintainer approval and execution procedure](maintainer-workflow.md#greet-resource-contacts) for each resource that meets either condition above. It owns the combined confirmation before any addition or publication actions. In the standard workflow, offer to add an entry and create its separate commit only after displaying a positive recommendation, rationale, proposed placement, and complete entry. Don’t request authorization again for covered actions. Standard approval covers only the local addition and commit, not pushing or submitting a pull request.

### Create Addition Commits

Once adding and committing are explicitly authorized, recheck the current list for duplication and add only the approved entry to `README.md`, following the placement and formatting guidance above. Run the required repository checks and create one commit per approved addition through the applicable commit workflow. Preserve unrelated working tree and index changes, and keep them out of these commits.

Use the following complete commit message, replacing the placeholder with the resource’s verified name:

```text
Add `<resource-name>`
```

Don’t let recipient uncertainty prevent an otherwise approved addition from being committed. After creating maintainer addition commits, continue with the patch inspection in [Bind Approved Additions to Commits](maintainer-workflow.md#bind-approved-additions-to-commits).

## Verify Maintainer Account

During workflow selection, don’t mention this check or its result, failure, or selected workflow unless the user asks. This affects narration only, not required tool approvals.

Run this read-only check once per invocation when a placement issue or a proposed addition or publication first requires workflow selection, using `gh`’s existing authentication for `github.com`:

```sh
gh api graphql --hostname github.com \
    --raw-field 'query=query { viewer { login } }' \
    --jq '(.data.viewer.login | ascii_downcase) == "porada"'
```

Enable the maintainer workflow only when the command exits successfully and prints exactly `true`. Otherwise, keep the standard workflow. Don’t require a user-run check or change authentication to enable it.

The check verifies the account authenticating the API request, not a Git author, repository owner, or browser session. Retain the result only for this invocation. After workflow selection, resume the calling step. Verification doesn’t change the inclusion standard or authorize mutations.
