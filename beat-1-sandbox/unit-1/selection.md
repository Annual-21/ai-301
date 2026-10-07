# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**[Issue link](https://github.com/codepath/pathreview-ai301-fa26-s1/issues/54)**

[The individual Path Review issue page. A link to the repository or the issue list
does not satisfy this field.]

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
````
I graded all three against the same installed rubric as before; its hash still starts with `b0dd57d90db7e36f`. The "Verdict rule" section is still blank, so I used the skill's default: accept only if every required check passes. All three issues are in the scoped repo. The repo isn't archived and was last pushed 2026-09-16, 20 days ago.
 
**#54 is accepted. #68 and #69 are still rejected.**
 
**1. #54: Resume section detection fails on text with leading whitespace. Accepted.**
- **Bounded newcomer scope: pass.** The repo owner opened it as one bug in `_detect_sections()`, with steps to reproduce and three named failing tests. It's labeled `good first issue`.
- **No active claimant: pass.** Nobody is assigned, and no pull request links to it, either formally or in the thread. The thread has about 10 classmates saying they'll take it. The house rule says classmates' claim comments don't block an issue, so I didn't count them. Without the house rule, those comments would fail this check as your rubric is written.
- **Ranking:** #54 is the only accepted issue, so it ranks first by default. Your fit profile is still empty, so I can't say how well it fits you.
- **Size:** one classmate, Natwange, reported that the fix also had to touch `_strip_markdown` to get two Markdown tests passing. The fix may be a bit bigger than the issue suggests, but no maintainer has said it touches core internals, so scope still passes.
 
**Rejected:**
- **#68 fails "No active claimant."** Pull requests #78 and #89 are linked to it and still open.
- **#69 fails "No active claimant."** Pull requests #87 and #91 are linked to it and still open.
 
```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/54",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass",
       "evidence": "Last push to any branch 2026-09-16T21:48Z, 20 days before 2026-10-06 (threshold 200)"},
      {"name": "Repo in use", "grade": "pass",
       "evidence": "archived: false; default branch main last pushed 2026-09-16 (20 days, threshold 90)"},
      {"name": "Bounded newcomer scope", "grade": "pass",
       "evidence": "Owner-filed single bug in _detect_sections() (line-start-anchored header patterns) with repro and 3 named failing tests; labeled good first issue"},
      {"name": "No active claimant", "grade": "pass",
       "evidence": "No assignee, no linked or mentioned PRs; thread claims are all from classmates (author_association NONE), which the Path Review house rule says not to count"}
    ],
    "verdict": "accept"
  }
]
````
 
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

[Run 1: 16/20, Run 2: 17/20, Run 3: 18/20, Run 4: 19/20 ]

**Issue analysis**

[### Issue-20: `excalidraw/excalidraw#11811`

**Rubric decision: Accept | Gold label: Reject**

My rubric incorrectly accepted this issue because it passed the maintainer activity, repository activity, contribution policy, and claimant checks. Excalidraw was actively maintained, with recent commits on the default branch, a recent push, and evidence of maintainer responses to other issues. 

However, the issue leaves important implementation decisions unresolved: the logo asset is still to be determined, and the implementation may require changes to both the editor's toolbar and element handling, as well as application-level wiring. The requested feature therefore involves more than a clearly isolated change, and its full implementation scope is not yet established. The absence of comments also means there is no discussion confirming the proposed design or clarifying the implementation boundaries.

This was a false accept. The issue demonstrates a weakness in my rubric which is describing a feature and listing its success criteria can make a task appear bounded even when important design and implementation decisions remain open. My scope check should distinguish between a feature that has a clear user-facing goal and one that is sufficiently defined for a newcomer to implement.]

**Check rationale**

[ "| Maintainer activity | Repo-facts block: "last push to any branch" date and the bundle's capture date | Pass if the last push is within 200 days of the capture date. | required |" 
This cleanly separates dead repositories. Using the capture date avoids ambiguity about whether “recent” should be measured from today. Release dates and issue-comment activity were removed because they were inconsistent across the bundles, and “human maintainer” was removed because maintainer status could not be verified from usernames alone. The check therefore evolved from requiring a human maintainer commit plus recent issue activity, to an either/or rule, then to a 500-day commit/release threshold, and finally to the current last-push-within-200-days rule.]

**Trade-offs**

[It no longer checks whether maintainers respond to issues, A repo pushed 150 days ago with no one reviewing Pull Requests passes and Any branch counts any push, including bot pushes or feature branches.Also, the partial --only run on 01, 09, 14, 16, 02, 07 and 17 came back 6/7, and the dead repos were still rejected]

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

[Answer all three:

1. The issue's fit to your interests and to the time available.
Answer: Issue #54 is a strong fit because it involves Python, regex/pattern matching, debugging, and running tests, all of which align with your computer science and software-development background. The issue is also clearly defined: _detect_sections() fails when text has leading whitespace, with three named failing tests and reproduction steps already provided. Given the available time, it appears manageable because the expected fix is focused on one function rather than a large feature.
2. What the verdict identified correctly, and what you weighed that the rubric could
   not.
   Answer: he verdict correctly identified that the repository is active, the issue has a small and well-defined scope, there is no linked PR, and the classmates' claim comments were correctly ignored under the house rule. However, the rubric could not account for my personal fit or rank the issue based on my interests and experience. It also did not evaluate labels, setup difficulty, or implementation difficulty. In addition, the classmate A classmate noted that the fix may also require changes in _strip_markdown, suggesting that the issue could be larger than it initially appears.
3. The anticipated difficulty in claiming it.
Answer: Claiming issue #54 may be competitive because about 10 classmates have already commented that they want to work on it. Although there is currently no PR, one could appear soon, as happened with #68, #69, and #73. The house rule allows multiple people to work on the same issue, but I will need to make my contribution stand out, especially because the actual fix may be somewhat larger than the issue description suggests.]

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
