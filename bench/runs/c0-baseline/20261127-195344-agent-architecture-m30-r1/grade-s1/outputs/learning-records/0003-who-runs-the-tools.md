# In quiz 0001's first attempt, Riley had the model running its own tools

Riley's answers show the belief that the model carries out tools itself (M4): it reads the booking system on its own, and runs three tools and answers within one model call.
This should be addressed before building further on the agent loop, since counting model calls (and so cost per request) and designing the program around the model both depend on it.

**Evidence:** quiz 0001, submission s1: q2 and q4 (M4). On q6, Riley also added that the model remembers its earlier tool choices across sessions on its own (M3). q1 (the loop defines an agent) and q3 (a step limit for a stuck agent) were correct, both as multiple choice.

**Implications:** This answers the open check in record 0002: as of s1, Riley had not shown that the program runs each tool or that every step is a separate model call.
q5 gave that the result goes back to the model, but not why.
M3 matters for the coming context and memory work.
s1 was taken on the day of the agent-loop session; the later attempt, s2, is not yet graded and may show whether any of this has changed.
