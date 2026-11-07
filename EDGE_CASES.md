# Edge cases and reproducibility

## Build request
Build Ghost Protocol in Shelled: a browser-local mystery with three clues, an unreliable AI witness, a contradiction timeline, a gated accusation and multiple endings. Persist progress locally and support reset.

## Observed results
- Shelled generated React and CSS for the investigation. The preview allowed collecting all three clues, asking two questions, marking three conflicts, and accusing ORACLE-9 to reach the best ending.
- Refreshing the Shelled preview preserved clue, question, conflict and ending state. The current witness response returned to its default after refresh even though asked-question markers persisted.
- An initial long project prompt produced a project name/type length error. A shorter project creation request followed by a detailed build prompt proceeded.
- Shelled's GitHub export reported failure after creating the repository and its initial .env.example; the remaining files were recovered via Shelled's archive export. The archive was committed separately; this is not evidence of a Shelled-created pull request.

## Reproduce
1. Open the public demo and start an investigation.
2. Collect all three clues, ask two questions, mark three conflicts, and accuse ORACLE-9.
3. Refresh; check that the ending and progress remain. Notice the console's current answer resets.
4. Use Reset Investigation and confirm progress resets.

## Limits
One ending and preview refresh were exercised. Other endings, cross-browser behavior, accessibility and mobile layouts have not been independently verified. The AI witness uses scripted responses, not live AI.

## Follow-up Shelled run
In the Ghost Protocol project in Shelled, the follow-up prompt was: “In the existing Ghost Protocol game, fix the observed persistence bug: preserve the last ORACLE-9 answer across refresh, including old saves with no answer. Keep the existing game, design, content, and all progress. Do not reset or replace the project.”

Shelled produced version 4 and opened [PR #2](https://github.com/0xChand/ghost-protocol-stranger-builds/pull/2). Its diff shows how the save format changed and how older saves get default values. In the Shelled preview, an existing version 3 save kept its progress. After asking “Define Ghost Protocol” in version 4 and refreshing, the answer and progress both remained. The [public game](https://app.shelled.ai/share/40b235cd-340a-4caf-93c7-77e608b7733a) still shows version 3, so judges can reproduce the original behavior there and test the fix from the PR.

To test the fixed build, run `gh pr checkout 2` in a clone of this repo, then `npm install` and `npm run dev`. Ask “Define Ghost Protocol” and refresh. Check that both the answer and the question count remain visible. A local production build of PR revision `27e0dbf533e8b1bcf4298c2c3d8b8dc14e6d593d` passed on November 7, 2026 with Node 24.12.0 and Next.js 14.2.35. GitHub Actions recorded a failure before the job started, so the local build is the recorded build check for that revision.

The first export failed while attempting to add a GitHub Actions workflow. Adding a workflow to the repository and selecting “Keep GitHub” for that file allowed the subsequent Shelled sync to finish. The service supplied only a generic export error, so the underlying cause is unconfirmed.
