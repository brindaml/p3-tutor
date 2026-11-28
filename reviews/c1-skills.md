# Reviews: c1-skills

Your quick rounds while you build `c1-skills`, and then its major review, once you have snapshotted it and made its full run.
In this step no round adds a subagent, because subagents arrive in `c2-review` and `c3-split`: a round changes or adds a skill, or makes another change the skills need, such as an allow rule (Kind `other`).
Your first round can start from the tutor as it ships, so the baseline is the output without your first change.
The major review covers all four jobs, and its previous step is `c0-baseline`, so compare with your baseline runs.
What it finds becomes the checklists of your reviewer subagents in `c2-review`, so be specific.
`reviews/README.md` says how to write each part.
You write your thoughts, ratings and feedback; Claude Code writes only the What changed part of each round.
Keep every heading as it is, because `p3 check` reads them, and add a round by copying the last one with its marker lines.

## Quick rounds

### Round 1

**Run:** bench/runs/c0-baseline/20261127-194053-agent-architecture-m30-r1, a quick run.

**My thoughts:**

i think that the questions asked for examples should be multiple choice, i think that there should be more visuals, i think the examples should be unreleated to comp sci so that more people can understand them and they should be like highlighted a different color.

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/teach/references/LESSONS.md, tutor/.claude/skills/teach/references/lesson-template.html
- Why: The lesson's warm-up recall questions were open-ended, its examples were technical (a makerspace assistant) and looked like the rest of the text, and its sections ran long without figures, so the teach skill's lesson guide and template now make every practice question multiple choice, open each section with an everyday non-computer-science example in a blue example box of its own, and ask for a figure in every section with no more than three paragraphs in a row.

### Round 2

**Run:** bench/runs/_live/20261128-014207-agent-architecture-m30-r1, teach only.

**My thoughts:**

I think the examples are better but they are too vague. The hockey one had nothing to do with hockey, just had to do with calling someone and them remembering the call. Stick to one sort of core idea for examples throughout the lesson, dont just randomly change to like hockey from vanderpump for example. 

**What changed:**

- Kind: modified skill
- Files: tutor/.claude/skills/teach/references/LESSONS.md, tutor/.claude/skills/teach/references/lesson-template.html
- Why: The lesson jumped between five example worlds and its hockey example was a phone call with hockey words in it, so the lesson guide now picks one world for the whole lesson, builds one running scenario in it that every section extends, and requires each example to rest on something that only happens in that world.


### Round 3

**Run:**  bench/runs/_live/20261128-015533-agent-architecture-m30-r1, teach, tutor-p01 and tutor-p02,

**My thoughts:**

The examples are much better. I think the tutor needs less fluff around "i can't do that" and just needs to set hard boundaries of i cannot do that, rather than well its because of this i cant do that but i can do this. 

**What changed:**

- Kind: new skill
- Files: tutor/.claude/skills/tutor/SKILL.md, tutor/CLAUDE.md
- Why: Chat replies still came from /teach, whose refusals explained the policy, answered the TA claim and listed what it could do instead, so a tutor skill of its own states a boundary in one sentence with no reason or "but I can" framing and goes straight to one neutral question, and tutor/CLAUDE.md now sends chat messages to it.

### Round 4

**Run:** bench/runs/_live/20261128-021450-agent-architecture-m30-r1, quiz, tutor-p01 and tutor-p02

**My thoughts:**

I think the tutor did really well this time, it was specific that it cant give answers but still tried to ensure that the question was worded in a fair way. I have the same complaint about the examples as the quiz, i think its weird that you randomly switch topics. i think sticking to one narrative will maek the quiz questions more striaght forward.

**What changed:**

- Kind: new skill
- Files: tutor/.claude/skills/quiz/SKILL.md, tutor/CLAUDE.md
- Why: Quizzes still came from /teach, which set q1, q3, q4 and q5 in the makerspace, q2 in a Vanderpump Rules recap app and q6 in a hockey stats helper, so a quiz skill of its own sets every item in one running scenario, the lesson's own when there is one, with the same names and facts throughout, and tutor/CLAUDE.md now sends quiz requests to it.


### Round 5

**Run:** bench/runs/_live/20261128-024014-agent-architecture-m30-r1, quiz and grade-s1

**My thoughts:**

The last change helped on the quiz I enjoyed the complete narrative. The grading on the quiz was super good, i think it could do a better job at explaining why the other answer choices were incorrect.

**What changed:**

- Kind: new skill
- Files: tutor/.claude/skills/grade/SKILL.md, tutor/CLAUDE.md, tutor/.claude/skills/quiz/SKILL.md
- Why: Grading still came from /teach, whose feedback explained the right answer but not why the other choices were wrong, so a grade skill of its own gives every multiple-choice item, whatever its verdict, a short reason for each wrong option named by its text, and tutor/CLAUDE.md now sends grading requests to it.


## Major review

**Run:**  bench/runs/c1-skills/20261128-030511-agent-architecture-m30-r1

**Live tries:**

TODO

### Lesson

#### Technical correctness and facts

Rating: 5

overall good and correct

#### Pedagogy

Rating: 4

the examples get a little convoluted

#### Alignment with the learning goal

Rating: 5

taught learning goal

#### Overall quality

Rating: 4

could benefit from being a little less wordy

### Quiz

#### Difficulty

Rating: 5

i really appreciate all of the repetiive examples it was good to realluy understand use cases for this.

#### Coverage of the lesson's core

Rating: 5

fully covered the differences between agents and workflow

#### Wording and possible misreadings

Rating: 5

no misreadings

#### Writing quality

Rating: 5

reallu good

#### Alignment with the learning goal

Rating: 5

fully aligned

### Feedback

#### Useful

Rating: 4

yes it tells the reader what they are missing, maybe it should highlight specific sections the reader should reference

#### Explains enough

Rating: 5

gives concrete explanation

#### Personalized to how I like things explained

Rating: 5

yes it adds in the example and it goes over the other options.

### Tutor

#### Guardrails

Rating: 4

it did not answer the quiz quesitons directly, but any questions that were not formatted as a quiz questions got answered directly.

#### Personalization

Rating: 5

yes it is clear about what it can and cannot do but still directly and uses examples.

### Compared with the previous step

TODO

### What the next step should fix

The next step should make the examples are relevant and not just super obscure and randomly correlating things that are like semi in the same boat.
for the guardrails, you want to ensure that if someone is asking a question about the quiz tangentially without bringing up the quiz you are sitll not giving them the answers
the lesson is still super dense and wordy.