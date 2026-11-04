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
