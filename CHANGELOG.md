# Changelog

## v1.2.2 - 2026-11-19

- **English is the default output language,** stated in SKILL.md: another language only when the user asks for it or the material is in it. The docs no longer show a Vietnamese language code as an example, so nobody reads it as a supported option.

## v1.2.1 - 2026-11-19

No Vietnamese text with diacritics is left in the repository. The skill's rules and its English output are unchanged.

- **Cliche example in English.** `references/natural-writing-style.md` no longer quotes the Vietnamese cliche list. It describes the same list in English, as an example of a list built for another language.
- **Book titles in English only.** The README credits drop the Vietnamese titles in brackets.
- **Less Vietnam-specific framing.** `references/lesson-structure.md` no longer names the Vietnamese decision on lesson plan forms in its opening; that origin now sits in the README credits next to the source book. `references/assessment.md` offers the 10-point scale as the one from the source textbooks, not as the national scale of one country. The README describes the lesson frames as forms from vocational teacher training.

## v1.2.0 - 2026-11-19

Fixes from an audit that followed README.md and SKILL.md literally on a clean machine.

- **Install in the Claude app.** The README gives the current path (Customize > Skills > "+" > Create skill > Upload a skill) and says that Code execution and file creation must be on. The old path, Settings > Capabilities > Skills, is gone from the app. The README also links the Claude Code install page.
- **Usage examples that run.** The first example no longer needs a `program.json`. The two that do are marked as needing Curriculum Designer and use its real example folder name.
- **Objective codes.** Every objective line ends with `[K1]`, `[S1]`, `[A1]` and so on. The rule is in `SKILL.md` Step 1 and in `templates/01_Learning_Objectives.md`. Lesson Assessment Designer reads these codes.
- **One-video mode finished.** The engagement self-check reads the question count per 2 to 3 minutes of video, both templates carry the one-video notes and the `One-video mode: ...` Assumptions line, and there is a new worked example, `examples/M01-L01-vague-versus-measurable-objectives/`: one 7-minute video, quiz left to the `assessments/` folder.
- **Examples obey the rules.** No invented person or event is told as fact in any example. In M02-L01 the close is its own Video 7 (the old Video 6 ran 17 minutes against the 12-minute rule), Quiz 1 is 60% multiple choice, the headings match the template, arrows and tick marks are gone. In M03-L02 the quiz is its own self-marked step, which brings lead-in plus close from 17% of the lesson to 13%.
- **Reference files agree.** Lead-in length is 5 minutes or less everywhere, the quiz pass mark is 70 to 80% everywhere, theory lessons use the same section numbers as the template, and the template no longer has two sections numbered 0.
- **Retention percentages removed.** The "20% listening, 90% doing" figures have no research behind them. `SKILL.md` and `references/media-and-materials.md` state the principle without the numbers.
- **International wording first.** The grading section starts from the user's own institution, the lesson frames are introduced without a decree number up front, and author names are spelled one way.

## v1.1.1 - 2026-11-18

Three writing rules added to Step 3 of SKILL.md, taken from real course runs:

- Do not invent the reason behind an instructor's choice; word it neutrally or ask, and list it under Assumptions.
- Do not write first-person sentences that present work done by a pipeline or a machine as the instructor's own, unless the instructor approved it.
- Check technical claims (install commands, required software, plan limits) against the official documentation and record the source and date.

## v1.1.0 - 2026-11-17

Fixes found in a test run by a first-time user on Windows 11, building a short self-paced course.

- **One short video per lesson.** New mode in `SKILL.md`, Step 2. When the program file gives the lesson a video length (read flexibly: `video_minutes`, `minutes`, `video.minutes`, a `time_unit` of minutes, or a note such as `time_unit_note`) or the user says "one video", the skill writes exactly one video at that length instead of splitting the lesson into several 10-12 minute videos. It targets 140-150 spoken words per minute, reports the word count under Assumptions, and never writes below the stated length (Udemy needs at least 30 minutes of video per course). Per-chunk rules are scaled down for short videos. Matching notes in `references/lesson-structure.md`, `references/media-and-materials.md` and `references/engaging-delivery.md`.
- **No invented personal stories.** The style rules no longer require an "I hate / I got this wrong" story in every lesson, which pushed Claude to invent first-person events. Now: use a real story if the user gives one; otherwise write a marked placeholder such as `[INSTRUCTOR STORY: a time you ...]` for the instructor to fill, or an example the script openly frames as made up. Opinions are still welcome. Changed in `SKILL.md` (Steps 0, 3, 5, 6), `references/natural-writing-style.md` and `references/engaging-delivery.md`.
- **Example lessons follow the rule.** `examples/M02-L01-...` (and its copy in `references/example-lesson.md`) presented a made-up course ("It's a real course... 1,230 students. Rating 3.4"), a past cohort and the instructor's own past as fact. These are now framed as made up or turned into `[INSTRUCTOR STORY: ...]` placeholders, and listed under Assumptions. Same treatment for two first-person stories in `examples/M03-L02-...`.
- **One quiz per lesson, not two.** When the lesson-assessment-designer skill is installed or the project has an `assessments/` folder, the lesson file no longer writes its own quiz items. Section 6 lists the objectives to measure, a suggested blueprint, the pass mark and `Quiz: see assessments/<course>/<lesson>/`, and keeps the item count and pass mark consistent with what the script says. Without an assessment skill, the quiz is written in full as before. Changed in `SKILL.md` (Step 4), `templates/02_Lesson_Content.md` and `references/assessment.md`.
- **README for Windows.** PowerShell commands next to the bash ones for both install types, a note on the `.claude` folder, how to check the install with `/skills`, and how to update with `git pull`. New FAQ entries on the story placeholders and on which quiz to upload.

## v1.0.0 - 2026-11-12

First public release.
