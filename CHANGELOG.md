# Changelog

## v1.1.0 (2026-11-17)

Fixes found in a test run by a first-time user on Windows 11, building a short self-paced course.

- **One short video per lesson.** New mode in `SKILL.md`, Step 2. When the program file gives the lesson a video length (read flexibly: `video_minutes`, `minutes`, `video.minutes`, a `time_unit` of minutes, or a note such as `time_unit_note`) or the user says "one video", the skill writes exactly one video at that length instead of splitting the lesson into several 10-12 minute videos. It targets 140-150 spoken words per minute, reports the word count under Assumptions, and never writes below the stated length (Udemy needs at least 30 minutes of video per course). Per-chunk rules are scaled down for short videos. Matching notes in `references/lesson-structure.md`, `references/media-and-materials.md` and `references/engaging-delivery.md`.
- **No invented personal stories.** The style rules no longer require an "I hate / I got this wrong" story in every lesson, which pushed Claude to invent first-person events. Now: use a real story if the user gives one; otherwise write a marked placeholder such as `[INSTRUCTOR STORY: a time you ...]` for the instructor to fill, or an example the script openly frames as made up. Opinions are still welcome. Changed in `SKILL.md` (Steps 0, 3, 5, 6), `references/natural-writing-style.md` and `references/engaging-delivery.md`.
- **Example lessons follow the rule.** `examples/M02-L01-...` (and its copy in `references/example-lesson.md`) presented a made-up course ("It's a real course... 1,230 students. Rating 3.4"), a past cohort and the instructor's own past as fact. These are now framed as made up or turned into `[INSTRUCTOR STORY: ...]` placeholders, and listed under Assumptions. Same treatment for two first-person stories in `examples/M03-L02-...`.
- **One quiz per lesson, not two.** When the lesson-assessment-designer skill is installed or the project has an `assessments/` folder, the lesson file no longer writes its own quiz items. Section 6 lists the objectives to measure, a suggested blueprint, the pass mark and `Quiz: see assessments/<course>/<lesson>/`, and keeps the item count and pass mark consistent with what the script says. Without an assessment skill, the quiz is written in full as before. Changed in `SKILL.md` (Step 4), `templates/02_Lesson_Content.md` and `references/assessment.md`.
- **README for Windows.** PowerShell commands next to the bash ones for both install types, a note on the `.claude` folder, how to check the install with `/skills`, and how to update with `git pull`. New FAQ entries on the story placeholders and on which quiz to upload.

## v1.0.0 (2026-11-12)

First public release.
