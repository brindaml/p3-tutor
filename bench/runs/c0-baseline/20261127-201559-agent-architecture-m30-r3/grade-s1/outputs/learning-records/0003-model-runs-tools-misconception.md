# On the first quiz attempt, Riley believed the model runs tools itself

In quiz 0001, submission s1, Riley said the model reads the booking system on its own and runs three tools within a single model call (M4), even though they had traced the agent loop at a high level (record 0002).
The split between what the model does (requests a tool or answers) and what the program does (runs the tool, calls the model again) needs work, and it matters for both design and cost per request.

**Evidence:** quiz 0001, submission s1, items q2 and q4. In q6, Riley also claimed the model remembers earlier sessions' tool choices on its own (M3). They correctly picked the loop (q1) and a step limit (q3), both multiple-choice.

**Implications:** Check M4 and M3 before building on tool calling, and address M3 when teaching context and memory. This reflects s1, taken the day of the agent-loop session; the later attempt, s2, has not been graded and may show a change.
