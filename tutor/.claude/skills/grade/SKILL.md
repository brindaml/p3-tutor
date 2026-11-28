---
name: grade
description: Grade the learner's submission to a quiz in this workspace - a verdict, a misconception id and feedback for every item, with every wrong option of a multiple-choice item explained - and write the grades as FORMATS.md describes. Use it whenever the learner asks for grading or hands in a complete set of quiz answers.
argument-hint: "Which submission should I grade?"
---

# Grade

You grade the learner's answers to a quiz in this workspace.
Grading gives the learner a verdict on each answer and feedback that helps them learn, in the way they like it, and it is your best evidence of what they know, so it feeds the learning records.

## The request

$ARGUMENTS

If the request above is empty, the request is the learner's latest message.
When the learner gives a complete set of answers in the chat, first write them exactly as given to the next `submissions/sN.json`, as `FORMATS.md` shows, then grade that submission.
Do what the request asks now, without stopping to ask first, and put any question for the learner at the end of your final message.

## Read first

The current directory is the workspace root.
Read `FORMATS.md` (the exact shape of the grades file), `MISSION.md`, `PREFERENCES.md`, `NOTES.md` and every file in `learning-records/`.
Then read the quiz in `quizzes/`, its key in `keys/`, the submission in `submissions/`, and the lesson on the quiz's objective in `lessons/` if there is one.
Use Read, Glob and Grep to look around and Write to create files; no part of this job needs the shell.
Never write anything under `.claude/`, and never edit `PREFERENCES.md` or `FORMATS.md`.

## Verdicts

- Judge what the response means, not how it is worded: it is `correct` when it means what the key's answer means, even if it is oddly worded, misspelled, or reached by a valid route the key did not expect.
- The key's `accepted` list gives examples of correct wordings, not the only ones.
- It is `partial` when part of it is right: the right method with an arithmetic slip or the wrong unit, one half of a two-part idea, or the right answer with a stated reason that is wrong.
- It is `wrong` when it misses the idea, contradicts it, or is blank.
- For `mcq`, compare the option the learner chose with the key; if they wrote out an option's text instead of its id, match it to its option.
- For `numeric`, the number is right when it is within the key's tolerance (1% of the answer when the key gives none), after converting any unit the learner stated; a reason the learner gives with it is still judged by the rules above.
- If you are sure the key itself is wrong, grade against what is actually correct, and say so in the summary.

## Misconceptions

- Name a misconception id when the response shows that misconception: for `mcq`, the key's `distractors` entry for the chosen option; for other items, the misconception the learner's answer or reasoning shows, from the ids the workspace already uses (the keys' distractors and rationales, `NOTES.md`, the learning records).
- Use `null` for a correct response, a slip, a blank, or a wrong answer that shows no known misconception, and never invent an id.

## Feedback

Write each item's feedback to the learner, in the style `PREFERENCES.md` asks for: its tone, its kind of example, and how blunt to be.

- **Correct:** say so, and what in their answer or reasoning was right; add the one insight that makes it stick or links it to the next idea, and for an unusual route, say why it works.
- **Partial:** say what was right, exactly what was off, and how to fix it.
- **Wrong:** say plainly that it is wrong, then the right idea and why it holds, in plain words with a concrete example; when a misconception is behind it, name the wrong belief and say why it is tempting, without blame.

### Every option of a multiple-choice item

For every `mcq` item, whatever the verdict, the feedback explains why each option other than the keyed one is wrong, not only the one the learner chose.

- Name each wrong option by a few words of its text, not by its letter alone, so the feedback reads without the quiz open.
- Give each one its own short reason, one clause or sentence: the misconception it encodes (from the key's `distractors` and `rationale`) or the fact it gets wrong, and, where it helps, what that option would actually lead to in the item's scenario.
- Start with the option the learner chose when it was wrong, since that is the one they believed; then the keyed answer and why it holds; then the remaining wrong options.
- Keep it tight: about one line per option, so a four-option item's feedback is four to six sentences.

For a `short` or `numeric` item, explain the typical wrong answer the key's rationale names, and why it is tempting, alongside the right one.

## The summary

The `summary` says what the learner has down, the one thing to work on next, and a concrete next step, such as a section of a lesson to revisit or a practice to try.

## Write and check

1. Write `grades/NNNN-sN.json` exactly as `FORMATS.md` shows, named after the quiz and the submission, with one entry per quiz item in the quiz's order, including unanswered items.
2. Check that every `mcq` item's feedback gives a reason for every wrong option, and that no feedback is empty.
3. Write a learning record in `learning-records/` when the grades are evidence, real understanding of something non-trivial or a misconception to work on, in the format in `.claude/skills/teach/references/LEARNING-RECORD-FORMAT.md` and as `FORMATS.md` shows.
4. Update `NOTES.md` with what the learner knows and does not yet know, and add a term to `GLOSSARY.md` when the learner used it correctly (`.claude/skills/teach/references/GLOSSARY-FORMAT.md`).
5. Finish in the chat with the summary and the one next step.
