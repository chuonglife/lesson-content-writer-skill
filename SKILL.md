---
name: lesson-content-writer
description: Write the complete teaching content for ONE lesson plus a separate learning objectives file, from a course outline, training program, syllabus or raw material. Produces a one-page lesson plan, a word-for-word instructor script, examples, questions with answers, demonstrations, practice tasks, a quiz or skill rubric, a slide outline and ready-to-use handouts, using vocational teaching frames (theory, practical, integrated lessons; Introduce-Present-Apply-Check) and 4-part measurable objectives. For live classes, online classes and self-paced video courses (Udemy, Teachable, LMS). Use it whenever the user asks to write a lesson, lesson plan, lecture, teaching or video script, lesson objectives, "flesh out lesson 3", "write module 2 lesson 1", "turn this outline into a lesson", or hands over material and says "make this lesson", even without saying "lesson plan". For a whole program use curriculum-designer instead.
---

# Lesson Content Writer

Turn the source material for one lesson (a program file, a syllabus line, a textbook chapter, slides, rough notes) into two files: a learning objectives file that states what learners will be able to do, and a lesson content file that a learner can read to understand and an instructor can pick up and teach tomorrow. Run it lesson by lesson to complete a whole course.

The method comes from vocational teacher training: the lesson plan forms, teaching methods, active learning techniques and media rules taught to vocational instructors, condensed into the reference files below. It is strict about structure and about measurable objectives, and loose about content, which is where the writing goes.

## What you produce

Two Markdown files in `lessons/<course-slug>/<Mxx-Lyy-lesson-slug>/` in the user's working folder:

| File | Content | Template |
|---|---|---|
| `01_Learning_Objectives.md` | Lesson facts, objectives in Knowledge / Skills / Autonomy and responsibility written with the 4-part formula, the competency element, learner products, an alignment table objective > where taught > how checked, assumptions | `templates/01_Learning_Objectives.md` |
| `02_Lesson_Content.md` | One-page plan, then the full lesson in teaching order (spoken script, examples, questions with answers, procedures, demonstrations, practice, consolidation, homework), assessment, materials (slide outline, sheets), post-lesson reflection | `templates/02_Lesson_Content.md` |

Write in the language of the user's request or of the course material. If they differ, ask once or follow the course. English is the default.

If the user wants the files somewhere else or wants a single file, do that instead; the content rules stay the same.

## Who the learners are

Learners differ from course to course, so do not assume. Find them in this order: (1) a market research or learner persona file for the course, if one exists; (2) the target learners section of the program file (`program.json` from the curriculum-designer skill has `target_learners`); (3) the material the user gave you; (4) ask. Write the result into the lesson facts table of `01_Learning_Objectives.md`.

Every example, scenario, task and product must come from the learners' own work world: the tools they use, the people they serve, the mistakes they make. The pedagogy sources use examples from welding, electronics and nursing. Translate them into the learners' trade. A lesson for support agents uses tickets and angry customers; a lesson for nurses uses wards and patient charts; a lesson for teachers uses lesson plans and classrooms.

## Workflow

### Step 0. Read the source and pin down the brief

1. Read all the material the user gave for this lesson. If the lesson belongs to a program file, read the module objectives, the lesson objectives, the lesson content outline, the hours, the delivery conditions and the assessment method, and look at the lessons before and after it.
2. Write down, making reasonable assumptions where needed and listing them at the end of `01_Learning_Objectives.md`: lesson title; previous lesson; duration (1 theory hour = 45 minutes, 1 practice hour = 60 minutes, 1 assessment hour = 60 minutes, unless the user's institution uses another rule); **lesson type** (theory, practical or integrated, see `references/lesson-structure.md` section 1); who the learners are and what they already know; delivery mode (live, live online, self-paced video, blended).
3. When the user's request and the program file disagree (delivery mode, group size, duration), the user's request wins; note the difference under Assumptions.
4. Stop and ask only when two readings would produce two different lessons (for example a 2-hour live class versus two 10-minute self-paced videos).

### Step 1. Write `01_Learning_Objectives.md`

Read `references/learning-objectives.md`. Every objective line follows **(1) action verb + (2) object + (3) conditions or context + (4) performance standard**. Lead sentence: "By the end of this lesson, learners will be able to:". Three groups: Knowledge, Skills, Autonomy and responsibility. No more than 3 specific objectives per 45 minutes. No unmeasurable verbs (understand, know, learn, be aware of, be familiar with, appreciate). A standard is something an instructor can check by looking, counting or comparing.

If the program file already has objectives for the lesson, keep their intent and rewrite them with all four parts. You may make a standard tighter or more specific than the program file says, never looser and never contradictory; note the numbers you chose under Assumptions. Build the alignment table now. It steers steps 2 to 4.

### Step 2. Design the sequence (the one-page plan)

Read `references/lesson-structure.md` for the frame that matches the lesson type:
- **Theory**: Lead-in > New content (split into chunks, each run through **Introduce - Present - Apply - Check**) > Consolidation > Self-study assignment.
- **Practical**: Lead-in > Initial instruction (1/4 to 1/3 of the time: review, procedure with checkpoints and key points, demonstration, common mistakes) > Ongoing coaching (more than half) > Closing debrief > Self-practice.
- **Integrated**: Lead-in (a problem situation) > Topic introduction > Problem solving (just-enough theory in IPAC cycles, procedure and demonstration, practice with a skill check sheet) > Problem close > Self-study.

For each activity pick a lead method, a technique and the media, using `references/teaching-methods.md` (quick-choice table) and `references/active-learning-techniques.md` (by position in the lesson and by group size). Pacing rules: no stretch of pure listening longer than 15 minutes; change grouping at least twice; every piece of media comes with something learners do with it. Minutes must add up to the lesson duration.

**Time conventions.** Count learner minutes. Minutes a learner spends paused on an Apply task count toward that chunk. Reference ratios: practical lesson, initial instruction 1/4 to 1/3 and practice over 50%; integrated lesson, theory at most 40%, practice and self-checking at least 45%, lead-in plus close at most 15%; theory lesson, chunks of 7 to 15 minutes with Apply and Check taking at least a third of each chunk. To convert script length to time use 150 spoken words per minute (sources give 100 to 200) and note it under Assumptions.

How minutes are counted for the ratios: settling in, review, lead-in, consolidation and the self-study briefing count as "lead-in plus close"; topic introduction, theory chunks (including their Apply and Check), procedure explanation and demonstration count as "theory"; supervised practice, role plays, the skill check and learner self-checking count as "practice". Live sessions longer than 90 minutes get a 10-minute break per 90 minutes, shown in the plan and kept outside the lesson minutes.

**Self-paced video courses.** The frame stays; it maps like this. Each chunk (one unit of knowledge, or one task of the initial instruction) becomes **one video of 10 to 12 minutes or less** with its own opening, body and close. Settling in, review, lead-in and topic introduction go into **Video 1**. Consolidation and the self-study assignment go into the **last video**. The Check of each chunk becomes a **pause question** whose answer is given right after the pause. A **quiz** follows each group of theory videos. A **submitted assignment** replaces supervised practice and the instructor gives feedback through the platform. Live-class rules translate: "20% of the class tries a step" becomes "every learner tries it at the pause"; "change grouping" becomes alternating watch, answer, do, submit, read the Q&A; "if nobody answers" becomes the explanation after the pause for those who got it wrong; the board plan becomes a screen plan. Add a "Video n / Quiz / Assignment" note to every row of the one-page plan. `references/example-lesson.md` shows a complete case.

### Step 3. Write the teaching content (most of file 02)

This is the part learners read and instructors say, so write the full subject content. Never leave a heading with nothing under it. Read `references/engaging-delivery.md` first.

- **Lead-in**: one of the 11 options (a real story from the learners' work, a surprising figure with a source, one of the 6 kinds of problem situation, try-before-you-learn, a short clip with the question asked before playing it), 5 minutes or less, checked against G-L-O-S-S, ending with the lesson title, the objectives as a concrete promise and the lesson structure.
- **Each chunk**: *Key teaching points* (key terms, main idea, the core, 6 lines max; this is the slide or board content) > Introduce > Present (clear explanation, a correct example, a wrong or near-miss example, a diagram as a table or in words, links to what learners already do) > Apply (a 2 to 5 minute task on the learners' own material) > Check (a question with its answer) > Lock-in (3 key terms) > a one-sentence bridge.
- **Procedures and skills**: a step table with what to do, tools, checkpoint or key point, pass criterion; three demonstration runs (normal speed, slow with what, how and why, summary); at least 20% of the class tries a step; a common mistakes table with cause and fix; practice on a sheet with a task brief that answers the 7 questions (who, what, where, how long, with what, what product, how presented and assessed).
- **Script** written as it will be said: first person, short sentences, stage directions such as `[pause]`, `[ask the room]`, `[show slide n]`, `[write on board]`. Not textbook prose.
- **Questions**: 8 to 15 per 45 minutes of *theory* time, written out, each with its expected answer and what to do if nobody answers; mix recall, processing and application. Practice time is checked by the check sheet and by 1 or 2 debrief questions per practice round, not by the per-45-minute count.
- **Role plays and scenarios**: give the fixed starting material that makes rounds fair (the customer's opening message, the case facts, the time limit), never the learner's lines. If the lesson depends on rules the source does not give (a company playbook, a hospital protocol, a school policy), write them as clearly marked placeholders such as `[your refund rule]`, or as fictional rules flagged under Assumptions, never as if they were the real policy.
- **Numbers in the script**: stories and illustrations may carry concrete names and odd numbers. Anything that will only be known in class (how many learners got it right, the cohort's average) is a placeholder such as `[say the real count]`. Data presented as real (ratings, research results) must come from the source or be left out.
- **Consolidation**: learners summarize first (one-minute paper, 3 key terms, a quick mind map), then the instructor locks in against the objectives and links to real work tomorrow.
- **Self-study**: a task with a product, a due date, a how-to and criteria; core and stretch levels; preparation for the next lesson.
- **Self-paced video**: each video holds one chunk with its own open, body and close; the script contains the pause prompts ("Pause the video now and..."); a quiz or assignment after every one or two videos. See `references/media-and-materials.md` section 8.

### Step 4. Assessment and materials

Read `references/assessment.md`. Every objective line gets an instrument. Theory and online lessons get an end-of-lesson quiz; practical and integrated lessons get a skill check sheet or product rubric whose criteria read *result noun + quality sign + indicator* and always include time, effectiveness and compliance or safety. Materials: a slide outline (one idea per slide, 6 lines max, 2 fonts max, 3 colors max) and the sheets (information sheet, task sheet, job sheet, check sheet) written out in full so they can be used as is, following `references/media-and-materials.md`.

### Step 5. Remove the AI voice (required, before the final review)

Read `references/natural-writing-style.md` and run its final tests on all of `02_Lesson_Content.md`. The result must read like a real instructor wrote it for their own class: names, odd numbers, opinions, sentences of uneven length. No em dashes, no stock phrases, no tidy triplets everywhere, no bold scattered through the script, no summary sentence closing every section. The plan, sheets and criteria stay in a plain formal register; the script stays spoken. Do not mix the two voices.

### Step 6. Self-review before handing over

Run three checklists: the end of `references/learning-objectives.md` (objectives), section 8 of `references/engaging-delivery.md` (engagement), and this one:
- Every content section serves at least one objective; every objective is taught somewhere and checked somewhere.
- Minutes add up; the section ratios for the lesson type hold.
- Terms match the program file and earlier lessons of the same course.
- No invented sources, figures or quotations. Teaching-science figures come only from the reference files. When the lesson is itself about teaching (objectives, methods, slides, video lessons), the reference files may be used as subject content. A source the program lists but the skill does not summarize may be named, not quoted.
- Every sheet, checklist or clip the script mentions exists in the lesson's materials section.
- All examples come from the learners' own work world.

Tell the user: the two file paths; a short plan (one line per top-level activity: name, minutes, video/quiz/assignment if any); the lesson type you chose; the assumptions.

## Quality guards learned from real reviews

These rules came out of reviewing produced lessons with simulated learners. Each one fixed a mistake that happened more than once.

- **Name before you point.** Write "these four verbs" only after the four verbs have been named in the same video or section. Each video may be watched alone.
- **Pauses match.** If the script says "pause the video, take 60 seconds", any on-screen label says 60 seconds too.
- **Answers get their own beat.** The answer to a pause question is shown and said on its own slide or paragraph, not squeezed into the summary.
- **Every task is fully listed where it is given.** If learners must fill a sheet at a pause, all of its fields are on screen or in the sheet; due dates and where to download are stated.
- **Do not cite by number alone.** "Criterion 2" means nothing to a listener; say what criterion 2 is.
- **Counts match.** "Two exercises", "three things", "five models" at the start must match what is given at the end.
- **Keep the head noun on slides.** "Slides alone are not enough", not "Alone not enough".
- **No made-up sample data.** Where real data is not available, tell learners how to fill the cell themselves.
- **Lock-ins are read in full.** Each point that appears as a bullet in the lock-in is said in full at that moment, followed by a 3 to 4 second pause.

## Writing several lessons in a row

One lesson at a time, one folder each. Before writing lesson n, read the objectives files of the earlier lessons of the same course (if they are not written yet, use the earlier lessons' objectives and content outline from the program file): do not reteach, use the product of the earlier lesson as the input of this one, keep the same voice and terms. The review at the start of lesson n comes from the objectives of lesson n-1. Vary the lead-in: two lessons in a row must not open the same way.

## Principles

- **The frame is fixed, the content is creative.** Never drop the Check, the consolidation or the homework.
- **Teach less, teach it well.** Only the theory needed to do the job; readable material becomes active reading with questions.
- **Learners do, not only listen.** Retention runs from about 20% for listening alone to about 90% when learners see, say and do.
- **Write for the instructor who teaches tomorrow morning.** Sheets, questions, answers and criteria must be usable as written. Never "the instructor prepares their own".

## Reference files

- `references/learning-objectives.md`: the 4-part formula, verb tables, 6 kinds of performance standard, source examples, worked examples, checklist.
- `references/lesson-structure.md`: choosing the lesson type; theory, practical and integrated frames; 11 lead-ins and G-L-O-S-S; the IPAC cycle; sequences by content type; initial instruction; mapping to self-paced video.
- `references/teaching-methods.md`: quick-choice table; lecture, demonstration, guided questioning, discussion, 3/4/6-step practical teaching, problem-based learning, case method, projects; how to write methods into the plan.
- `references/active-learning-techniques.md`: 32 techniques by position and group size; the 7-question task brief; writing scenarios.
- `references/media-and-materials.md`: choosing and using media; slides; board; handouts; video; live online and self-paced video.
- `references/engaging-delivery.md`: pacing by the attention curve; openings; explaining so it sticks; questions; keeping learners doing; closings; script voice; engagement checklist.
- `references/assessment.md`: oral questions at 3 levels, written tests, 4 objective item types, practical assessment, criteria, check sheets, grading.
- `references/natural-writing-style.md`: what AI-sounding text looks like, what to write instead, the two voices, final tests, other languages.
- `references/example-lesson.md`: one complete lesson for calibrating length, density and voice.
- `templates/01_Learning_Objectives.md`, `templates/02_Lesson_Content.md`: the two output frames. Keep the template's headings and labels exactly (the bold structural labels such as **Introduce**, **Ask** and **Lock-in** do not count toward the "3 bold spots per section" limit of the style rules; that limit is for the script text). For integrated lessons, number the sections: 1 Lead-in, 2 Topic introduction, 3 Problem solving (3.1 Task 1 theory chunks, 3.2 Task 2 procedure and demonstration, 3.3 Task 3 practice and skill check), 4 Problem close, 5 Self-study.
