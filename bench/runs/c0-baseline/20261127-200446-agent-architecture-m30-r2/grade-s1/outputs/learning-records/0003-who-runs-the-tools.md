# On the first quiz attempt, Riley had the model running the tools itself

Riley recognised the agent loop and the need for a step limit, but answered as if the model runs tools itself (M4), so the model-call count came out as 1 instead of 4.
Riley also added that the model remembers its earlier tool choices across sessions on its own (M3).

**Evidence:** quiz 0001, submission s1: q1 and q3 correct; q2 and q4 show M4; q6 partial with M3; q5 gave what happens to a tool result but not why.
This attempt was made on the day of the agent-loop session. The later attempt, s2, had not been graded when this was written.

**Implications:** Unless later evidence shows these are fixed, revisit the split between model and program, one model call per step, before building on it (it also drives cost per request).
When teaching memory, address M3 directly: the program has to save information and give it back to the model.
