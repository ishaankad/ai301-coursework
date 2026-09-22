# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/53

**Verdict output**

```text
Ranked candidates:
1. issue-53 — accept — "Strong first issue with bounded scope, reproducible failures, clear tests, and strong learning value."
2. issue-60 — accept — "Safe and highly discoverable, but very small and provides limited learning value."
3. issue-37 — accept — "Safe docs-only task, but acceptance criteria and implementation scope are under-specified."

{
  "issue-53": "accept",
  "issue-60": "accept",
  "issue-37": "accept"
}
```

---

## Eval iterations

**Run history**

Run 1: Initial grading of the three candidate issues based on their issue pages.

Run 2: Compared scope boundedness, blast radius, discoverability, definition of done, learning value, and effort estimate across all three candidates.

Run 3: Re-checked the candidate differences and selected `issue-53` because it combines a bounded change with existing failing tests and a clear red-to-green workflow.

**Issue analysis**

For `issue-53`, the main concern was a mismatch between the narrow issue title and the broader set of listed failing tests. The title describes the missing `(555) 123-4567` format, while the tests appear to cover additional phone-format and start-of-text behavior. A contributor following only the title could implement a narrower fix and still have failing tests.

For `issue-60`, the issue is extremely bounded and easy to reproduce, but the root cause is already explained in the issue body. That makes it useful as a first-ever PR exercise but gives the contributor less opportunity to investigate or reason about the code.

For `issue-37`, the task is docs-only and names the relevant files, but the definition of done is less concrete. The issue asks for descriptions and examples without providing a documentation template or reviewer checklist.

**Check rationale**

The grading criteria emphasize bounded scope, low blast radius, discoverability, a clear definition of done, learning value, and a realistic effort estimate. `issue-53` has a particularly strong combination of these because it includes a reproducible bug and named failing tests, allowing the contributor to verify completion through pytest rather than relying mainly on reviewer judgment.

**Trade-offs**

Selecting `issue-53` means accepting some additional risk because regex changes can over-match. The issue should therefore clarify the intended test scope and ideally include a negative test to ensure unrelated strings are not redacted.

`issue-60` is safer and simpler, but its small scope and already-explained diagnosis reduce its learning value. `issue-37` has similarly low technical risk, but its documentation acceptance criteria require more reviewer judgment.

---

## Selection rationale

**Selection rationale**

1. I picked `issue-53` because it has a concrete bug, a reproducible failure, and four named tests that give the contributor a clear definition of done.
2. The task is contained to a single module and focuses on one regex-related behavior, so the scope is still manageable for a first issue.
3. It provides stronger learning value than `issue-60` because the contributor has to reason about the existing regex and regression tests rather than simply applying a diagnosis already provided in the issue.
4. Before assigning it, I would clarify the title and test scope so the contributor knows whether the task covers only parenthesized phone numbers or the additional formats represented by the tests.
