# Maintainer Workflow

## Greet Resource Contacts

Identify greeting recipients for each committed resource, reusing evidence from its assessment.

A greeting notifies a resource contact about its inclusion. It doesn’t establish authorship. Select verified individual accounts in this priority order:

1. Resource authors, preserving supported coauthorship.
2. Explicitly identified package maintainers, when authorship remains uncertain.
3. The individual owner of the canonical repository, when neither authors nor package maintainers can be established.

Keep each recipient’s supported role explicit. Don’t add fallback contacts merely to expand a greeting whose authors are already established. Stop once suitable recipients are verified, unless concrete conflicting evidence could change the selection.

### Resolve Resource Identity

Establish the canonical repository and the relevant package or component. Inspect the package’s own manifest rather than assuming a root manifest describes it. For npm packages, [`repository.directory`](https://docs.npmjs.com/cli/v12/configuring-npm/package-json/#repository) can locate the package inside a monorepo. Retain discovered former names, directory moves, repository transfers, and predecessor projects when relevant to tracing origin.

### Find Direct Attribution

Start with the package manifest, package-specific README credits, and authors or maintainer files. npm’s [`author` and `contributors` fields](https://docs.npmjs.com/cli/v12/configuring-npm/package-json/#people-fields-author-contributors) are distinct from registry maintainer metadata. A declared author isn’t necessarily the sole creator or current maintainer, and organizational credit doesn’t identify an individual. npm can derive `contributors` from an `AUTHORS` file, so those sources may repeat the same credit rather than corroborate it independently.

When a person is explicitly credited as an author, verify their GitHub account and stop if that resolves the attribution. Don’t reconstruct the entire history unnecessarily.

For the maintainer fallback, require an explicit designation for the relevant package in its manifest, README, maintainer file, or canonical documentation, then verify the individual’s GitHub account. Registry publish access, organization membership, code ownership, or recent commits alone don’t establish that designation.

### Verify GitHub Accounts

Prefer an explicit GitHub profile link or GitHub’s account association on a relevant commit. In [REST commit responses](https://docs.github.com/en/rest/commits/commits#list-commits), distinguish raw `commit.author` metadata from the associated account in `author.login` and from the separate committer fields. Use the author association as evidence, not an assumption of sole authorship. Don’t infer a handle from a matching real name, email prefix, or npm username.

Inspect a pull request’s contribution before assigning credit. Opening or merging it doesn’t establish sole implementation authorship. Preserve substantive coauthorship, including work submitted or merged through automation.

### Trace Origin When Needed

Use bounded package-specific implementation history and relevant pull requests when missing or conflicting attribution leaves recipient selection unresolved. Don’t reconstruct an entire history merely to greet a verified maintainer or repository owner. Filter commits by the relevant path and branch. Account for pagination rather than treating one page as complete history. Follow discovered predecessor paths when relevant, without assuming path filtering follows renames automatically.

Find the change that introduced the actual integration, distinguishing original implementation from a rename, relocation, fork import, or bulk migration. Stop when the evidence supports attribution. Don’t use a fixed score or rank people by commit count. Discount dependency bumps, formatting sweeps, release automation, generated changes, and unrelated monorepo work without discarding substantive coauthorship.

### Distinguish Other Roles

Don’t describe a maintainer, code owner, or repository owner as an author without authorship evidence. Recent substantive package work can support only a **likely maintainer** inference.

Inspect ownership rules only when they resolve a material ambiguity. [GitHub code ownership](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners) assigns review responsibility, not original authorship. On the relevant branch, GitHub uses the first file found in this order: `.github/CODEOWNERS`, root `CODEOWNERS`, then `docs/CODEOWNERS`. Within that file, the last matching pattern wins. Evaluate relevant implementation files, not only the manifest. Preserve differing file owners, follow a documented custom ownership system’s semantics when applicable, and never choose an arbitrary member of a team.

### Verify Repository Ownership

Confirm that the repository is canonical for the listed resource, including the specific package in a monorepo. Verify its current `owner.login` and `owner.type` through the GitHub API. The fallback requires `owner.type` to be `User` and no conflicting evidence that makes the account an inappropriate resource contact. A username-looking URL alone is insufficient. Don’t select an arbitrary member of an organization or team.

Label this recipient as the **repository owner**, and state that original authorship was not established. Keep the repository identity and ownership evidence with the recipient selection.

### Present Greetings and Offer Posting

Before preparing greetings, exclude the account that passed [maintainer verification](../SKILL.md#verify-maintainer-account) from the selected recipients using a case-insensitive GitHub login comparison. Keep the attribution evidence and any other verified recipients. If no recipients remain for a resource, omit its greeting and posting offer, explain that no external recipient remains, and don’t seek fallback contacts merely to produce a greeting.

For each committed entry with verified recipients, identify the resource and output one greeting in its own fenced code block, replacing the placeholder with the verified handle:

```text
👋 @<recipient-handle>
```

For multiple supported recipients, place their handles alphabetically on the same greeting line, separated by single spaces. Outside the block, give each recipient’s supported role and decisive evidence link. Include competing attribution or a limitation only when it materially affects whom to greet.

If only an organization, team, unverified identity, or insufficient evidence is available, omit the greeting and explain the limitation. Inaccessible evidence doesn’t prove that no author exists.

For each resource with a prepared greeting, retain a conversation-local mapping from its name and URL to its approved `README.md` addition, verified recipients and roles, exact greeting, and addition commit’s full SHA. Inspect the recorded commit’s patch to establish that mapping. Show the corresponding full commit permalink in `porada/awesome-vitest` beside each greeting. Commits used as authorship evidence in a resource’s own repository are never posting destinations.

After presenting at least one mapping, offer to post the greetings after the user pushes the commits. Present the greetings and posting offer as one batch. One explicit approval may cover the displayed batch. Skip the offer only when posting that exact batch is already authorized. The user handles the push. Approval to add or commit entries doesn’t authorize comments, and a report that the commits were pushed doesn’t authorize comments either. Posting approval given before the push remains pending until the user confirms publication and the remote checks below succeed.

### Verify Published Destinations

Use `gh` with the same existing `github.com` authentication used for maintainer verification. Before posting the batch, repeat only the [maintainer verification command](../SKILL.md#verify-maintainer-account) and require a successful `true` result. Otherwise, stop and report that posting requires verified maintainer authentication, without switching accounts or posting through another integration.

Before each comment, verify the complete resource, recipient, body, and commit mapping against GitHub:

1. Address `porada/awesome-vitest` explicitly, using the recorded full SHA rather than `HEAD`, a branch tip, commit order, a matching title, or the CLI’s default repository.
2. Confirm that the full SHA is in the current published `main` history. A commit that resolves through the API isn’t sufficient, and an earlier addition commit need not be the branch tip. For a GitHub comparison, use the addition SHA as the base and the current `main` tip as the head, requiring `ahead` or `identical`.
3. Read the remote commit’s actual `README.md` diff and confirm that it adds the approved resource with the expected name and destination URL. Compare it with the recorded addition, not merely the commit message or current file contents. If the patch is unavailable or incomplete, obtain sufficient read-only evidence before proceeding.
4. Confirm that the recipients, supported roles, and exact greeting still match the approved mapping. Resolve any conflicting recipient evidence before posting.

If publication can’t be verified, wait for the user rather than pushing or posting. If an amend, rebase, squash, or other change replaced the SHA, don’t select a substitute automatically. Inspect the proposed replacement, present the revised mapping, and obtain approval for that destination. Changed recipients or comment text also require approval of the revised mapping. Unchanged, verified mappings don’t need another confirmation.

### Post and Verify Comments

Post one greeting at a time, as a commit-level comment without a file or line attachment. Before posting, inspect that commit’s existing comments for an equivalent greeting to the same recipients, accounting for pagination. If one already exists, report its permalink instead of duplicating it. If a relevant existing comment conflicts with the approved greeting, ask before replacing or supplementing it.

Use the verified repository and full SHA explicitly, and send only the approved greeting as the comment body. Verify the returned comment’s repository, commit SHA, body, and author’s `user.login` against the approved mapping and verified posting account before continuing to the next resource. Report each successful comment’s permalink.

If a request times out or its outcome is uncertain, inspect that exact commit’s comments before any retry. If the result remains uncertain, stop and report it rather than risk a duplicate. On any destination, body, or posting account mismatch, stop the remaining batch and report what was posted. Don’t delete, edit, or repost a comment as an automatic repair. Removing a comment cannot reliably undo notifications already sent.
