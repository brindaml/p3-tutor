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
  `s2` was graded on 2026-11-27 (`grades/0001-s2.json`); `s1` has not been graded.
- From s2, to work on:
  - M4 (the model runs tools itself): shown in the q4 reason, despite a correct q2 (learning record 0004).
  - M6 (an agent needs no stopping condition): q3, chose to let a stuck agent run longer.
  - Tool choice: named only the tool's name, not its description or parameters (q6).
- Suggested next step: trace the two-part laser cutter request, labeling each line "model" or "program" and marking where the loop would be stopped. Check these gaps before or at the start of context and memory.
- Next in the mission is context and memory, because the makerspace assistant has to answer from long machine manuals and remember each student's training status between visits.
