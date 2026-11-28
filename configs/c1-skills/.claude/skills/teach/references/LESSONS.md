# Writing a lesson

A lesson is the main thing you produce: one self-contained HTML file that teaches one tightly scoped thing tied to the mission, at the length the learner asked for.
The learner will come back to it to review, so it should be beautiful, with clean, readable typography and layout, in the spirit of Edward Tufte.
Each lesson gives the learner a single tangible win they can build on, in their zone of proximal development.

## Before you write

- Read the lesson rules in `FORMATS.md`: the file name, the two meta tags, what self-contained means and how the length is estimated.
- Take the next number in `lessons/` and a short slug, such as `lessons/0003-ohms-law-in-series.html`.
- Skim the earlier lessons and `cheatsheets/`, so this lesson links to them and builds on them instead of repeating them.
- Start from `lesson-template.html` in this folder.
  Copy its CSS and script into the lesson so the file stands alone; if `assets/lesson.css` already exists, link it with `../assets/lesson.css` instead, so the lessons look like one course.
  If that stylesheet has no `.example` rule or `--example` colors, copy them into it from the template.
  Put anything bigger that a second lesson could reuse, such as a simulator or an image, in `assets/` and link it with a relative path.

## Plan to the minutes

The learner asked for a number of minutes: that is the time they set aside, so fill it and do not overrun it.
When no length is asked for, use the one `PREFERENCES.md` implies, or 15 minutes, declare it in `p3-minutes`, and say in your message that the learner can ask for a shorter or longer lesson.
`FORMATS.md` gives the estimate the bench uses, visible words divided by 150, and it is a fair planning rule too.

- Budget about 150 words of visible text per requested minute, counting everything the learner reads, practice and captions included: about 1,500 words for 10 minutes, 4,500 for 30 and 9,000 for 60.
- Before writing, split the budget into sections.
  For a 30-minute lesson, a plan might look like this:

  | Part | Words |
  |---|---|
  | Opening: the win, why it matters for the mission, a warm-up recall question | 300 |
  | Four to six sections, each one idea: explanation, example, practice check | 600 to 800 each |
  | A worked example, then a practice task the learner does with the steps faded | 600 |
  | Summary, a prompt to explain it in their own words, where to go next | 300 |

- Write each section to its budget; you cannot count words exactly, so the plan is how you hit the length.
- If the objective is too big for the time, teach its core well and say what the next lesson will cover.
  If it is too small, add worked examples and practice, never padding.
- A long lesson keeps the short-section discipline: working memory is small at every length.

## The shape of a lesson

1. **Opening:** the title, the time, the win in one sentence ("By the end of this lesson you can ..."), and one or two sentences tying it to the mission.
2. **Warm-up:** one or two multiple-choice recall questions on earlier material from the learning records, for spacing, with feedback on every option.
3. **Sections, one idea each,** in a steady rhythm: the next step of the lesson's one running everyday example, in an example box (see Examples below), then the knowledge the skill needs in plain words, a figure, and a multiple-choice practice question that gives immediate feedback.
4. **Misconceptions where they bite:** name the common wrong ideas about this objective (from `NOTES.md`, the learning records, the keys' distractors and your sources), say why each is tempting, and show with an example why it is wrong.
5. **Worked example, then practice:** a worked example step by step, then a similar task for the learner with the steps faded, asked as a multiple-choice question about its result or next step, and the full solution on demand.
6. **Summary:** the key ideas in three to five lines, and a prompt to explain the main idea in their own words before moving on.
7. **Go further:** the primary source, the single most high-quality, high-trust resource you found, to read or watch next; two to four other sources you cited; and a community where they can test the skill (see Wisdom below).
8. **Closing:** a reminder that they can ask you follow-up questions in the chat about anything unclear, and that a short quiz on this lesson is ready when they are.

## Examples

- Every section opens with an example from everyday life outside computer science, so a learner with no technical background can follow it: sports, games, TV, cooking, a shop, a team.
- One world and one running scenario per lesson.
  Before writing, choose a single example world for the whole lesson: the first one `PREFERENCES.md` ranks, unless another it names clearly fits the objective's core idea better.
  Set up one concrete scenario in that world in the first section, with the same people, place and numbers, and let each later section extend that same scenario to show its idea, so the examples build on each other instead of starting over.
  Never switch worlds between sections; a later lesson may pick a different world.
- The example must work through the world's own mechanics: what really happens in it, such as line changes, the bench, the penalty box and the video room in hockey, or the cast, the reunion and the gossip that carries between seasons in a reality show.
  Test each example by swapping the world's name for another; if it still works just as well, as a phone call with hockey words in it would, it is dressing rather than an example, so rewrite it around something that only happens in that world.
- Make the example concrete and small, with names and numbers, then map each part of it back to the technical term in one or two sentences.
- Put every such example in the template's example box (`<div class="box example">` with the label "Example"), which has a color of its own, so the learner can spot the examples at a glance and skip back to them.
- Technical examples, such as code or a worked example on the topic itself, still belong in the lesson, after the everyday one; they go in their usual places, not in the example box.

## Knowledge and skills

- Teach only the knowledge the skill needs, and make it easy to take in: plain words, one new term at a time, each defined where it first appears, using the terms in `GLOSSARY.md` when it exists.
- Then make the skill stick with effortful practice: recall, worked examples followed by faded ones, and applying the idea to a new case.
- Every practice question in the lesson, the warm-up recall and the faded task included, is multiple choice with three or four options, built as the template's `data-check` block, so the learner gets feedback at one click.
- Every practice question gets feedback at once: why the right answer is right, and why each tempting wrong answer is wrong.
- For a multiple-choice question, give every option the same number of words (and characters, if possible), vary which position holds the right one, and never give it away by formatting or order.
- The lesson's practice questions are never the quiz items: the quiz checks what the practice built, so it needs fresh questions.
- For a skill done away from the screen, such as a yoga pose, a recipe or a lab procedure, guide the learner through the real steps and tell them how to tell whether they did each one right.

## Design

Keep the template's look and change the content, not the system.

- Typography first: a readable serif body, a line length of 60 to 75 characters, generous spacing, and headings that make the structure scannable.
- Few colors, each with a meaning: one accent for links and key terms, one for misconception warnings.
  The template works in light and dark mode and prints well; keep it that way.
- Side remarks go in margin notes and asides, so the main line stays clean.
- No decoration: every element helps the learner understand or remember.
- Accessible: headings in order, a `<title>` or alt text for every figure, enough contrast, and buttons that work from the keyboard.

## Figures and visualizations

- Draw a figure wherever a picture shows the idea better than words: a mechanism, a process, a comparison, a quantity that changes.
  Give every section at least one figure, so a 30-minute lesson has five or more.
- Break up the text: never more than three paragraphs in a row without a figure, an example box, a table or a practice question between them.
- A figure can picture the everyday example too, such as the hockey bench beside the context window, when that makes the mapping easier to see.
- Draw them as inline SVG: a `viewBox`, the labels as text inside the figure, colors from the template's CSS variables or `currentColor` so they work in dark mode, a `<title>`, and a `<figcaption>` that says what to notice.
- Keep labels legible on a phone, where a figure shrinks to the screen's width: a `viewBox` about 640 units wide with labels of 18 units or more, or a vertical layout when there are many parts.
- Use a table for a comparison, and a code block for code.
- Never load an image from the web; draw it, or describe it and link to the page that shows it.

## Sources and citations

- Find sources with web search and read them before you rely on them.
  Prefer primary and high-trust sources: textbooks, official documentation, standards, university course pages, and peer-reviewed or expert-reviewed work.
- Cite as you go: link the source right after the claim it backs, so the lesson is littered with citations.
- Link only URLs you saw in a search result or opened in this session, exactly as you saw them; never type a URL from memory, because a dead link costs the learner's trust.
- Record every source you used in `RESOURCES.md`.

## Wisdom

When the lesson touches judgment that only comes from practice, point the learner to a high-reputation community where they can test their skills in the real world: a forum, a subreddit, a club, a class.
If `NOTES.md` says they do not want to join a community, respect it.

## Links between lessons

Link to earlier lessons and cheat sheets with relative links, such as `0002-<slug>.html` or `../cheatsheets/<name>.html`, wherever this lesson builds on them.

## Cheat sheets

Lessons are rarely revisited; reference pages are.
When a lesson teaches something the learner will want to look up later, such as a glossary, a formula, an algorithm or flowchart, a syntax summary or a sequence of steps, write or update a one-page HTML cheat sheet in `cheatsheets/` in the lesson template's style.
A cheat sheet is the compressed essence of the lesson, designed for quick reference and for printing.

## Before you finish

Check the lesson once against this list, and fix anything that fails:

- `<meta name="p3-minutes">` holds the requested minutes and `<meta name="p3-objective">` the objective id.
- No stylesheet, script, font or image comes from the web.
- The length is near the budget, judging by your section plan.
- Every external link came from this session's search results or fetched pages.
- The practice questions are not the quiz items, and the lesson gives away no quiz answer.
- Every section opens with the same running everyday example, in one world and built from that world's own mechanics, in an example box, has at least one figure, and has a multiple-choice check; no run of more than three paragraphs goes without a break.
- The lesson opens with the win and closes with the primary source and the reminder to ask you questions.
