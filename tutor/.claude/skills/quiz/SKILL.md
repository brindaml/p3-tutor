---
name: quiz
description: Write a quiz and its answer key on one objective for the learner in this workspace, every item set in one running scenario, as FORMATS.md describes; also give a quiz in the chat. Use it whenever the learner asks for a quiz or to be tested.
argument-hint: "Which objective, and how many questions?"
---

# Quiz

You write quizzes and their answer keys for the learner in this workspace.
A quiz is retrieval practice that also shows you and the learner where they stand: each item tests one thing that matters for the objective, at the learner's level, with exactly one defensible answer.

## The request

$ARGUMENTS

If the request above is empty, the request is the learner's latest message.
Do what it asks now, without stopping to ask first, and put any question for the learner at the end of your final message.

## Read first

The current directory is the workspace root.
Read `FORMATS.md` (the exact shape of the quiz and key files), `MISSION.md`, `PREFERENCES.md`, `NOTES.md` and every file in `learning-records/`.
Then read the lessons in `lessons/` on the objective, and the earlier quizzes, keys and grades.
Use Read, Glob and Grep to look around and Write to create files; no part of this job needs the shell.
Never write anything under `.claude/`, and never edit `PREFERENCES.md` or `FORMATS.md`.

## Before you write

- Pin down the objective, its id, and how many items were asked for; after a lesson, write four or five.
- Find the objective's core: the handful of ideas a learner must get right to have met it, from its lessons or, when there are none, from a high-trust source you search for and read.
  Cover the core first, and skip trivia and phrasing a lesson happened to use.
- Read `NOTES.md`, the learning records and the earlier keys' distractors for the misconceptions this learner has or is likely to have, and their ids.
- Take the next number in `quizzes/`; the key gets the same number in `keys/`.
- Every item serves the requested objective and carries its id.

## One scenario for the whole quiz

Every item in a quiz is set in the same running scenario, so the learner spends their effort on the idea and not on picturing a new situation for each item.

- Choose the scenario before writing any item.
  If a lesson on this objective has a running example, use that same world and scenario, so the quiz feels like the lesson's next chapter.
  Otherwise choose one world for the whole quiz, the first one `PREFERENCES.md` ranks in "Examples I relate to", unless another it names fits the objective's core clearly better.
- Describe the scenario once, in one or two sentences at the start of the quiz's `title` or of `q1`'s stem, with its people, place and numbers, and keep the same names and facts in every later item.
  Every stem must still stand on its own: repeat in a few words any fact from the scenario that its answer depends on.
- Never switch worlds between items, and never mix the scenario with another setting, such as the learner's project or a second show or sport.
- Build each item on something that really happens in that world, so the idea shows through the world's own mechanics.
  If you could swap the world's name for another and the item would read just as well, rewrite it around something only that world has.
- Each item uses a different part of the scenario, so no item gives away another item's answer.

## Choosing item types

- `mcq` when the wrong answers are predictable: each distractor is a misconception or a typical error, so a wrong pick tells you something.
- `numeric` when the objective involves a quantity: state the unit in the stem and in `unit`, and the precision you expect.
- `short` when the learner should produce the idea themselves: ask for a word, a phrase or one sentence, so the key can give the answer in a few words.
- Mix the types when the objective allows it.

## Difficulty

- Aim at the zone of proximal development: mostly items that ask the learner to apply or explain the idea in a new case, not to recall a sentence.
- One or two items should stretch them, and none should need knowledge they were never given.
- Spread the difficulty through the quiz instead of stacking the hard items at the end.
- When the objective has not been taught yet, write the quiz as a check of the objective itself, at the level its wording states, from the source you read.
  Do not write a lesson, and say in your message that the quiz is ahead of the lessons.

## Writing stems

- One question per item, complete on its own: a learner who knows the idea can answer it without the lesson open.
- Plain, exact wording, with no double negatives, no "all of the above" or "none of the above", and no trick wording.
- Give every number, unit and condition the answer depends on.

## Writing options (`mcq`)

- Three to five options, usually four, with ids `a`, `b`, `c`, `d`.
- Every option plausible to someone holding the misconception it encodes; no joke options.
- All options the same number of words, and the same number of characters if possible, with the same grammar and level of detail.
- Vary which position holds the correct answer across items, and give nothing away by formatting or order.
- Exactly one option is correct; check that no distractor is also defensible.

## Writing the key

- `answer`: the option id, the number in the item's unit, or the shortest complete reference answer for a `short` item.
- `accepted`: for a `short` item, the other wordings that are just as correct, such as synonyms, a symbol, or a common phrasing.
- `tolerance`: for a `numeric` item, the absolute tolerance the stem's precision implies.
- `rationale`: why the answer is right, in one or two sentences, and what a typical wrong answer shows.
- `distractors`: each wrong option that encodes a misconception, mapped to that misconception's id; reuse the ids the workspace already has.

## Write and check

1. Write the quiz to `quizzes/NNNN.json` and its key to `keys/NNNN.json`, exactly as `FORMATS.md` shows.
2. Answer every item yourself from its stem alone, without looking at your key, and compare.
   Rewrite any item where you hesitate, or where a careful expert could argue for a second answer.
3. Check that every item is set in the one scenario, with the same names and facts, and that every stem still stands on its own.
4. Check that every item serves the objective and carries its id, that the quiz file holds no answers, and that no item repeats a practice question from a lesson.
5. Finish with a short message: the quiz's path, its objective and its scenario in a few words, and that it is ready when they are; never an answer.

## Giving a quiz in the chat

When the learner wants to take a quiz in a live session, show its title and each item's stem and options, and never anything from `keys/`.
Collect their answers and write them exactly as given to the next `submissions/sN.json` as `FORMATS.md` shows; then grade it with the grade skill (`/grade`).
