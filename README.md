# Lesson Content Writer: a Claude Skill that writes complete, teachable lessons with measurable learning objectives

**Lesson Content Writer is an open-source Agent Skill for Claude that turns a course outline or a syllabus line into one complete lesson: a learning objectives file and a lesson content file with a one-page lesson plan, a word-for-word instructor script, worked examples, questions with answers, demonstrations, practice tasks, a quiz or skill rubric, a slide outline and ready-to-use handouts.**

You point it at one lesson, for example "write Module 3, Lesson 2 of our support onboarding program". Claude reads the program, works out who the learners are, writes objectives an assessor can check, picks the lesson frame and the teaching methods, and writes the lesson out in full. An instructor can teach it the next morning. A learner can read it and follow.

It works in Claude Code, the Claude desktop and web apps, and the Claude Agent SDK. Live classes, live online classes and self-paced video courses (Udemy, Teachable, Coursera, Thinkific, any LMS). MIT licensed. It writes in the language of your request.

It is the companion of [Curriculum Designer](https://github.com/chuonglife/curriculum-designer-skill), which designs the whole program. Curriculum Designer gives you the modules and lessons; Lesson Content Writer fills each lesson. Next in the set, [Lesson Slide Designer](https://github.com/chuonglife/lesson-slide-designer-skill) turns each finished lesson into a slide deck (PowerPoint) and a video script.

## Contents

- [What you get](#what-you-get)
- [Who it is for](#who-it-is-for)
- [Install](#install)
- [Use it](#use-it)
- [How the skill works](#how-the-skill-works)
- [The three lesson frames](#the-three-lesson-frames)
- [The rules it enforces](#the-rules-it-enforces)
- [Example output](#example-output)
- [FAQ](#faq)
- [Sources and credits](#sources-and-credits)

## What you get

Two Markdown files per lesson, in `lessons/<course>/<Mxx-Lyy-lesson>/`:

| File | Content |
|---|---|
| `01_Learning_Objectives.md` | Lesson facts, learners, delivery mode; objectives in Knowledge, Skills, Autonomy and responsibility, each written as action verb + object + conditions + standard; the competency the lesson builds; what learners produce; an alignment table showing where each objective is taught and how it is checked; assumptions |
| `02_Lesson_Content.md` | A one-page plan with minutes, methods and learner actions; the full lesson in teaching order (lead-in, content chunks, procedures, demonstration, practice, consolidation, homework); the quiz or skill check sheet; a slide outline; the handouts written out in full; post-lesson reflection prompts |

A content chunk inside `02_Lesson_Content.md` looks like this:

```
### 2.3 The 4-part objective formula (12 min)

Key teaching points: Objective = verb + object + conditions + standard ...

Introduce: This is the one formula you have to know by heart today.
Present:   [show slide 13] Take the good objective from Video 1 and peel it apart ...
Apply:     Pause the video and fix these 3 broken objectives. Three minutes.
Check:     Ask: In "Write 3 course objectives on the template, each with all
           4 parts", which words are the conditions and which the standard?
           Answer: "on the template"; "3", "all 4 parts".
Lock-in:   4 parts. 6 kinds of standard. Measurable by eye.
```

## Who it is for

- **Teachers and lecturers** who need a full lesson plan and script, not a list of topics.
- **Corporate trainers and L&D teams** writing onboarding, product, compliance or soft-skills sessions.
- **Online course creators** on Udemy, Teachable, Coursera, Kajabi or Thinkific who want a script per video, pause questions and quizzes before recording.
- **Instructional designers** who want a first draft that already respects objectives, alignment and active learning.
- **Vocational and technical (TVET) instructors** who teach theory, practical and integrated lessons and must document them.
- **Nurse educators, coaches and workshop leaders** who teach procedures and need demonstrations and check sheets.

## Install

**Claude Code (personal, all projects)**

```bash
git clone https://github.com/chuonglife/lesson-content-writer-skill ~/.claude/skills/lesson-content-writer
```

**Claude Code (one project only)**

```bash
git clone https://github.com/chuonglife/lesson-content-writer-skill .claude/skills/lesson-content-writer
```

**Claude desktop or web app**

Download `lesson-content-writer.skill` from the [latest release](https://github.com/chuonglife/lesson-content-writer-skill/releases/latest) and add it under Settings, Capabilities, Skills.

No dependencies. The skill writes Markdown only.

## Use it

Ask in plain language. The skill triggers on requests about writing a lesson, a lesson plan, a teaching script or lesson objectives.

```
Write lesson 2 of module 3 from programs/support-onboarding/program.json.
Live class, 12 new hires, 2 hours.
```

```
I teach Year 10 biology. Here is my textbook chapter on osmosis. Turn it into a
50-minute lesson with objectives, a practical demo and an exit quiz.
```

```
This is my Udemy section outline for "Pricing your coaching packages".
Write the lesson as 4 short videos with pause questions and a quiz.
```

```
Write the learning objectives and full script for the lesson "Taking a manual
blood pressure reading" for first-year nursing students.
```

To fill a whole course, ask for one lesson at a time. The skill reads the objectives of the earlier lessons so it does not reteach and so each lesson builds on the last one's product.

## How the skill works

1. **Read the source and pin down the brief.** Lesson title, previous lesson, duration, learners and what they already know, delivery mode, and the lesson type: theory, practical or integrated. Gaps become stated assumptions.
2. **Write the objectives file.** Every line uses the 4-part formula. Three groups. At most 3 specific objectives per 45 minutes. An alignment table is built right away and steers the rest.
3. **Design the sequence.** The frame for the lesson type, a lead method and an active learning technique per activity, the media, and minutes that add up. No stretch of pure listening longer than 15 minutes.
4. **Write the teaching content.** Every chunk runs through Introduce, Present, Apply, Check and a Lock-in. Procedures get a step table, a three-run demonstration and a common-mistakes table. The script is written as it will be spoken.
5. **Write the assessment and the materials.** A quiz or a skill check sheet tied to each objective, a slide outline, and the handouts in full.
6. **Remove the AI voice.** A dedicated pass strips stock phrases, em dashes, tidy triplets and neutral filler, and adds names, odd numbers and opinions, so the script sounds like a real instructor.
7. **Self-review.** Objectives, alignment, minutes, terms, sources and engagement checklists.

## The three lesson frames

| Lesson type | When | Sequence |
|---|---|---|
| **Theory** | The objectives are mostly knowledge: concepts, classifications, principles, rules | Lead-in, New content in chunks (Introduce - Present - Apply - Check each), Consolidation, Self-study assignment |
| **Practical** | The objective is a skill or procedure and the knowledge was taught earlier | Lead-in, Initial instruction (1/4 to 1/3 of the time: procedure, checkpoints, key points, demonstration, common mistakes), Ongoing coaching (more than half), Closing debrief, Self-practice |
| **Integrated** | Just-enough theory, then practice in the same session, to build one competency | Lead-in with a problem situation, Topic introduction, Problem solving (theory in IPAC cycles, procedure and demonstration, practice with a check sheet), Problem close, Self-study |

The frames come from the lesson plan forms taught to vocational instructors in Vietnam. They were chosen because they force every lesson to have a lead-in, a check after each chunk, a consolidation and homework, which is exactly where AI-written lessons usually cut corners.

For self-paced video, each chunk becomes one video of 10 to 12 minutes or less, Checks become pause questions with the answer right after, quizzes follow groups of videos, and a submitted assignment replaces supervised practice.

## The rules it enforces

- **Objective formula.** Action verb + object + conditions + performance standard. "Set priority and status on 5 sandbox tickets, all correct against the SLA table" passes. "Understand ticket priorities" does not.
- **No unmeasurable verbs.** Understand, know, learn, be aware of, be familiar with, appreciate are rewritten into what the learner does to prove it.
- **Alignment.** Every objective is taught somewhere and checked somewhere. Every section serves an objective.
- **Check after every chunk.** A question with its expected answer and a fallback when nobody answers.
- **Learners do something every 10 to 15 minutes.** Think-pair-share, a quick write, a sort, a try-it step, a pause task.
- **Questions come with answers.** 8 to 15 written questions per 45 minutes, mixing recall, processing and application.
- **Materials exist.** Every sheet, checklist or clip the script mentions is written out in the lesson.
- **Examples come from the learners' own work.** Tickets for support agents, wards for nurses, lesson plans for teachers.
- **No invented sources or statistics.**
- **No AI voice.** No em dashes, no "delve", no "in today's fast-paced world", no triplets everywhere.

## Example output

A self-paced video lesson for teachers and trainers building their first online course, 150 learner minutes, 6 videos, 2 quizzes, 1 assignment: [examples/M02-L01-write-objectives-with-blooms-taxonomy](examples/M02-L01-write-objectives-with-blooms-taxonomy)

- [01_Learning_Objectives.md](examples/M02-L01-write-objectives-with-blooms-taxonomy/01_Learning_Objectives.md)
- [02_Lesson_Content.md](examples/M02-L01-write-objectives-with-blooms-taxonomy/02_Lesson_Content.md)

A live corporate training lesson for new customer support agents, produced by Claude from one request and the program file of the [Curriculum Designer](https://github.com/chuonglife/curriculum-designer-skill) onboarding example: [examples/M03-L02-live-chat-and-difficult-customers](examples/M03-L02-live-chat-and-difficult-customers)

## FAQ

### What is a Claude Skill?

A Claude Skill (Agent Skill) is a folder with a `SKILL.md` file and optional reference documents. Claude loads it when a request matches the skill's description, then follows its instructions. Skills run in Claude Code, the Claude apps and the Claude Agent SDK.

### What does this skill do that a plain "write me a lesson plan" prompt does not?

A plain prompt gives you a topic list with time stamps. This skill gives you the lesson itself: the spoken script, the examples, every question with its answer, the demonstration steps, the practice task brief, the quiz with explanations, and the handouts. The objectives are measurable, the minutes add up, every objective is checked, and the text is cleaned of the usual AI phrasing.

### What is the Introduce-Present-Apply-Check cycle?

It is the four-step loop each chunk of new content runs through. Introduce names the point and why it matters. Present explains it with a correct and a wrong example. Apply has learners use it right away for 2 to 5 minutes. Check asks a question to see whether it landed before moving on. It comes from vocational teacher training, where it is used for every theory section of a lesson plan.

### How does it write learning objectives?

With a four-part formula: action verb, object, conditions, performance standard. Verbs come from Bloom's revised taxonomy (Anderson and Krathwohl, 2001) for knowledge, Dave's levels for skills and Krathwohl's affective levels for autonomy and responsibility. Standards are one of six kinds: accuracy, time, product quality, compliance with a rule or template, quantity or rate, and correct sequence.

### Can I use it for Udemy, Teachable or Coursera video lessons?

Yes. Say the lesson is self-paced video. The skill splits it into short videos with their own opening and close, writes pause questions with answers, places quizzes after groups of videos and turns supervised practice into a submitted assignment with a check sheet.

### Does it work for corporate training and onboarding?

Yes. The second example is a live onboarding lesson for support agents. It takes the learner profile from your program file or your brief and uses scenarios from their real work.

### Does it work for school teachers?

Yes. Give it the chapter or the curriculum line, the year group and the period length. Use the theory frame for concept lessons and the practical frame for labs and procedures.

### Do I need the Curriculum Designer skill?

No. The skill works from any source: a syllabus, a textbook chapter, slides, rough notes. If you do have a `program.json` from Curriculum Designer, it reads the module and lesson objectives, hours and assessment method from it and keeps them consistent.

### What languages does it write in?

The language of your request or of the course material. The reference rules include a short method for building a list of AI clichés in any language before writing.

### Is it free?

Yes. MIT license. Use it, change it, build it into your own products.

## Repository layout

```
SKILL.md                                   instructions Claude follows
references/learning-objectives.md          4-part formula, verb tables, standards, checklist
references/lesson-structure.md             theory, practical, integrated frames; lead-ins; IPAC; video mapping
references/teaching-methods.md             choosing methods; lecture, demo, questioning, discussion, practical, cases
references/active-learning-techniques.md   32 techniques; the 7-question task brief; scenarios
references/media-and-materials.md          slides, board, handouts, video, online delivery
references/engaging-delivery.md            pacing, openings, explaining, questions, closings
references/assessment.md                   oral, written, objective items, practical check sheets
references/natural-writing-style.md        removing the AI voice
references/example-lesson.md               one complete lesson for calibration
templates/                                 the two output frames
examples/                                  generated sample lessons
```

## Sources and credits

- Vo Dinh Duong (2022), *Module 03: Preparing to Teach* (Mô-đun 03 Chuẩn bị dạy học), Ho Chi Minh City University of Technology and Education. Lesson plan frames for theory, practical and integrated lessons.
- Nguyen Van Tuan (2017), *Teaching Methods* (Phương pháp dạy học), and the Faculty of Technical Education (2007), *Teaching Methodology* (Giáo trình Phương pháp giảng dạy), Ho Chi Minh City University of Technology and Education.
- Nguyen Minh Trung, *Teaching Media* lecture notes, Vinh Long University of Technology Education.
- *Active Teaching Techniques*, compiled from Nguyen Van Cuong, Vietnam Upper Secondary Education Development Project (2006).
- Diep Phuong Chi (2026), course slides on training program development, Ho Chi Minh City University of Technology and Education. The 4-part objective formula.
- Anderson and Krathwohl (2001); Dave (1970); Krathwohl, Bloom and Masia (1964); Arnold, Lipsmeier and Ott (1998) for the 4-step and 6-step practical teaching methods.

The skill was first written in Vietnamese by Chuong for his own production line of online courses for teachers and trainers, tested on real lessons reviewed by simulated learners, then generalized and translated for public use.

## Contributing

Issues and pull requests are welcome, especially worked examples from other fields and AI-cliché lists for other languages.

## License

[MIT](LICENSE)
