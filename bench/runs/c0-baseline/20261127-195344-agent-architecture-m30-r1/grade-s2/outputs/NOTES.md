# Notes

## What Riley knows
- Python from classes: functions, lists and dicts, reading JSON, and calling a web API in one class project.
- Has used a chatbot for homework help and report drafts, and has noticed that it can state an outdated fact with confidence.
- A language model takes text in and writes text out, one token at a time, from patterns learned in training (learning record 0001).
- The agent loop at a high level: the model asks for an action, the action is carried out, the result comes back, and this repeats until it is done (learning record 0002).

## What Riley does not know yet
- Has never called a language model from code or written a tool definition.
- Has heard the words "token" and "context window" but cannot say what they limit or why they affect cost.
- Has not met memory, retrieval, workflows versus agents, or multi-agent systems.
- Has no machine-learning background beyond one statistics course.

## Working notes
- Quiz 0001 (the agent loop and tool calling) was taken twice: `submissions/s1.json` on the day of the agent-loop session, and `submissions/s2.json` four days later, from memory, as spaced practice.
  `s2` is graded (`grades/0001-s2.json`): q1, q2, q5 correct; q4, q6 partial; q3 wrong. `s1` has not been graded.
- From `s2`, to work on (learning record 0004): M4, said the model runs tools itself (q4 reason), despite choosing "outputs a request" in q2; M6, would let a stuck agent keep running (q3); thinks of tool choice as going by the name only, not the full description (q6).
- Shown in `s2` (learning record 0003): tool results go back to the model for its next call; counted the model calls correctly.
- Next in the mission is context and memory, because the makerspace assistant has to answer from long machine manuals and remember each student's training status between visits.
  First, do a short check on M4 and M6: trace a request, labelling each step "model" or "program", and say when the loop stops.
