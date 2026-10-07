# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Maintainer activity | Repo-facts block: "last push to any branch" date and the bundle's capture date | Pass if the last push is within 200 days of the capture date. | required |
| Repo in use | Repo-facts block: archived status | Repository is not archived, and either the default branch was pushed within the last 90 days | required |
| Bounded newcomer scope | Issue body and comment thread | Pass if the issue asks for one identifiable contribution with a reasonably concrete outcome. Fail only if it is explicitly an umbrella/tracking issue, primarily a usage/support question, the thread shows unresolved design debate about what should be built, or a maintainer states that the fix requires changes to core internals. A terse issue, missing reproduction steps, old issue, or lack of detailed implementation instructions does not by itself fail scope. | required |
| No active claimant | Repo-facts block: issue assignees and linked PRs; issue comment thread | No current assignee, no open linked PR addressing the issue, and no comment in the thread from someone saying they are working on it | required |
## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
