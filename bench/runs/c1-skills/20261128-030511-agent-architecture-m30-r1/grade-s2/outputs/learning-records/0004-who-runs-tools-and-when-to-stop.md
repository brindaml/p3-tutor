# Open: who runs the tools (M4) and why an agent needs a stop (M6)

Riley picked the right model output for a tool call (q2), but then explained the call count by saying the model runs one tool itself per call (M4), so the split between model and program is not yet solid.
Riley also chose to let a stuck agent keep running because it would eventually fix the bug (M6), even though record 0002 describes the loop ending at a final answer or a limit.
Revisit both before building on the loop; neither has been corrected yet.

**Evidence:** quiz 0001, submission s2, items q3 and q4.

**Implications:** Use a two-lane (model and program) diagram with a marked step limit, and tie the limit to the model budget.
In q6 Riley also said the model chooses a tool by its name alone, which matters for the mission goal of writing tool descriptions.
