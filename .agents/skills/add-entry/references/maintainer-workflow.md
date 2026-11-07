# Maintainer Workflow

## Greet Resource Contacts

Use this procedure whenever preparing maintainer approval for addition or publication actions, regardless of the assessment outcome or which actions have already completed. Prepare recipients and greetings before requesting approval, reusing evidence from the assessment.

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

### Prepare Approval Batch

Before preparing greetings, exclude the account that passed [maintainer verification](add-entry.md#verify-maintainer-account) from the selected recipients using a case-insensitive GitHub login comparison. Keep the attribution evidence and any other verified recipients. If no recipients remain for a resource, omit its greeting, explain that no external recipient remains, and don’t seek fallback contacts merely to produce a greeting.

For each entry with verified recipients, identify the resource and prepare one greeting, replacing the placeholder with the verified handle:

```text
👋 @<recipient-handle>
```

For multiple supported recipients, place their handles alphabetically on the same greeting line, separated by single spaces. Outside the block, give each recipient’s supported role and decisive evidence link. Include competing attribution or a limitation only when it materially affects whom to greet.

If only an organization, team, unverified identity, or insufficient evidence is available, omit the greeting and explain the limitation. Inaccessible evidence doesn’t prove that no author exists.

For each resource, retain a conversation-local mapping from its name and URL to the complete proposed `README.md` addition, category, complete [commit message](add-entry.md#create-addition-commits), verified recipients and roles, and exact greeting when available. The posting destination is that resource’s addition commit in `porada/awesome-vitest`. For an existing commit, inspect its patch and record its full SHA and permalink. For a planned commit, identify it by the displayed addition and commit message, then bind its SHA after creation. Commits used as authorship evidence in a resource’s own repository are never posting destinations.

Before offering a push to `main`, verify that the selected remote’s effective push destination is `porada/awesome-vitest` on `github.com`, and inspect the existing outgoing commit range together with the planned additions. If the destination differs, report the mismatch instead of offering the push. If pushing would include other commits or require a history rewrite, resolve that scope with the user before offering the push.

In every response requesting approval, present each complete current entry, including its description where applicable, and each exact greeting once, using the [entry presentation format](add-entry.md#deliver-results) and a separate fenced code block for each greeting. Include the category, complete commit message, exact push destination, and posting destination, with the full commit permalink when one exists. An entry or greeting already displayed in that response satisfies this requirement and must not be repeated beside the confirmation. Previews in earlier responses don’t replace the current preview.

Ask one confirmation covering the displayed batch’s remaining actions: adding the entries, creating one commit per addition, pushing those commits, and posting the prepared greetings as commit comments. Omit completed actions and explain omitted greetings. Honor narrower user limits and existing explicit authorization for the unchanged batch without asking again. A decision to include a resource doesn’t approve undisplayed entry wording or greetings. Approval of only some actions doesn’t authorize the others, and a report that commits were pushed isn’t comment approval. If the user will push the commits themselves, retain approval for the unchanged comment batch and resume verification when they report the push.

### Bind Approved Additions to Commits

After approval, create any planned commits through [Create Addition Commits](add-entry.md#create-addition-commits). Inspect each resulting commit’s patch and complete message against its approved addition, then record its full SHA and permalink in the mapping. This initial binding requires no further confirmation when the commit matches the approved content and scope. Resolve any mismatch before publication. Reuse verified mappings for existing commits.

### Publish and Verify Destinations

Once pushing is explicitly authorized, recheck the effective push destination and complete outgoing commit range, then use the verified remote and an explicit refspec to publish only the approved commits to `main`. If the destination changed or the push would now include unapproved commits or require an unapproved history rewrite, stop for a separate decision rather than expanding the approved batch. After the push, verify publication through the remote checks below before posting.

Use `gh` with the same existing `github.com` authentication used for maintainer verification. Before posting the batch, repeat only the [maintainer verification command](add-entry.md#verify-maintainer-account) and require a successful `true` result. Otherwise, stop and report that posting requires verified maintainer authentication, without switching accounts or posting through another integration.

Before each comment, verify the complete resource, recipient, body, and commit mapping against GitHub, reusing earlier patch evidence only as allowed in step 3:

1. Address `porada/awesome-vitest` explicitly, using the recorded full SHA rather than `HEAD`, a branch tip, commit order, a matching title, or the CLI’s default repository.
2. Confirm that the full SHA is in the current published `main` history. A commit that resolves through the API isn’t sufficient, and an earlier addition commit need not be the branch tip. For a GitHub comparison, use the addition SHA as the base and the current `main` tip as the head, requiring `ahead` or `identical`.
3. Confirm that the commit adds the approved resource with the expected name and destination URL, reusing the earlier patch inspection for the same full SHA. If that evidence is unavailable or insufficient, inspect the remote commit’s actual `README.md` diff against the recorded addition. A commit message or current file contents alone aren’t sufficient. If the remote diff is unavailable or incomplete, obtain sufficient read-only evidence before proceeding.
4. Confirm that the recipients, supported roles, and exact greeting still match the approved mapping. Resolve any conflicting recipient evidence before posting.

If publication can’t be verified, don’t post. For a failed push or an uncertain outcome, inspect the remote state before any retry and report what’s needed to continue. If an amend, rebase, squash, or other change replaced a bound SHA, don’t select a substitute automatically. Inspect the proposed replacement and obtain approval for the revised mapping through [Prepare Approval Batch](#prepare-approval-batch). Changes to approved entry content, recipients, or greeting text also require approval of the revised mapping. Unchanged, verified mappings don’t need another confirmation.

### Post and Verify Comments

Post one greeting at a time, as a commit-level comment without a file or line attachment. Before posting, inspect that commit’s existing comments for an equivalent greeting to the same recipients, accounting for pagination. If one already exists, report its permalink instead of duplicating it. If a relevant existing comment conflicts with the approved greeting, ask before replacing or supplementing it.

Use the verified repository and full SHA explicitly, and send only the approved greeting as the comment body. Verify the returned comment’s repository, commit SHA, body, and author’s `user.login` against the approved mapping and verified posting account before continuing to the next resource. Report each successful comment’s permalink.

If a request times out or its outcome is uncertain, inspect that exact commit’s comments before any retry. If the result remains uncertain, stop and report it rather than risk a duplicate. On any destination, body, or posting account mismatch, stop the remaining batch and report what was posted. Don’t delete, edit, or repost a comment as an automatic repair. Removing a comment cannot reliably undo notifications already sent.

## Complete Maintainer Threads

Evaluate the full thread, including recommendations made before earlier addition commits and additions the user requested despite a negative assessment. Treat as pending only inclusion decisions, approvals, or execution steps needed to finish positively recommended resources or other user-requested work. Explicitly omitted actions aren’t pending work.

When every positively recommended resource has reached its agreed completion point and no requested work remains, complete the current thread without another confirmation using the completion action and safeguards prescribed by the global **Thread cleanup** policy. This completion rule applies to the current thread regardless of who created it.
