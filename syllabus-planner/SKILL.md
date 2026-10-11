---
name: syllabus-planner
description: Turn one course syllabus (PDF, Word file, or pasted text) into a complete list of every graded item and its due date, with the exact syllabus line each date came from. Use this whenever a student shares a syllabus and wants to know what's due, when exams are, what to put in their calendar or planner, or "everything I have to turn in" for a class — even if they don't say "due dates". Also use it when someone asks to check a syllabus for missing or conflicting deadlines.
---

# Syllabus Planner

Turn one syllabus into a due-date list a student can trust. The whole value of this list is that it is **complete** and **nothing in it is made up**. A missed quiz costs the student points; an invented deadline teaches them not to trust the list. So when the syllabus is unclear, say so — never fill the gap with a guess that looks like a fact.

Every row you output carries a short quote from the syllabus so the student can check it in seconds.

## Scope

- One syllabus per run. If the student shares several, do them one at a time (one list per course).
- Output is a list in the chat. Don't add things to anyone's calendar or set reminders. If they ask, tell them they can copy the dated items into their calendar.
- No connectors or internet needed. Work only from the syllabus.

## Process

### 1. Read the whole syllabus first

Read every page, including tables, footnotes and the schedule at the end — schedules often hold most of the dates and are easy to skim past. Note:
- Course name and number, term and year (from the document content; if the file name disagrees with the content, trust the content and flag the mismatch).
- Class meeting days and times. You need these to turn "due before class" or "in class" into a time.

### 2. Inventory what counts toward the grade

Find the grading breakdown (weights, points). Make a private checklist of every component — homework, quizzes, exams, projects, participation, in-class exercises, extra credit, required-attendance sessions. **Anything that counts toward the grade is an item.** By the end, every component on this checklist must appear somewhere in your output: as dated rows, as a recurring rule, or under "No date given". This is your main defense against missing something.

### 3. Pull out every dated item

Walk the schedule line by line. Each individually dated graded item gets its own row — if there are 20 homeworks with 20 dates, list 20 rows. Students need each one, and rolling them into "weekly homework" hides real deadlines.

For each row:
- **Date** with weekday, e.g. `Wed Sep 2, 2026`. Check the weekday against the calendar for that year (if you can run code, compute it). If a date's weekday doesn't match the class meeting days, keep the date exactly as written and flag it — don't silently "fix" it.
- **Time** if stated or directly derivable from a stated rule (e.g. "due one hour before class" + class at 11:00 AM → 10:00 AM; say "derived" in the note). "In class" items get the class time. If no time is given, write `not stated`.
- **Quote**: the shortest syllabus text that proves the date.

### 4. Handle the hard cases honestly

These are where lists usually go wrong:

- **Rules, not dates.** "Due Friday at noon the week after release" is a rule. Report the rule once under "Recurring rules". Don't generate a list of Fridays — the release dates aren't in the syllabus, so those dates would be invented. An example in the syllabus ("e.g., the first one is due 2/6") illustrates the rule; it isn't an item.
- **Graded but undated.** If the syllabus grades something but gives no date ("dates announced on Moodle", "TBA", or simply nothing), list it under "No date given" with its weight. Don't borrow a nearby date.
- **Session labels aren't deadlines.** "Project workshop" or "Project work day" on a schedule is a class activity. Unless the syllabus says something is *due* that day, list the item under "No date given" and mention the session date in the note.
- **Inferred links.** If you connect a graded component to a scheduled session but the syllabus doesn't say so explicitly (e.g. a graded "Case competition – 10%" and a schedule entry "Mar 4: Case exercise in class"), keep the date and mark the link `(likely)` in the note.
- **Attendance that's graded.** Sessions where attendance changes the grade (required group sessions, triple-weight speaker classes) are items. Everyday participation is one recurring rule, not a row per class.
- **Conflicts.** If the syllabus contradicts itself on anything affecting a date, an item, or its weight (e.g. labs 10% in the grading table but 15% in the text), show both and flag it. Don't pick one.

### 5. Final check before answering

- Every grading component from step 2 is accounted for.
- Every dated row has a quote that actually contains (or clearly implies) that date.
- No row's date came from your assumption. If you can't point to the text, move it to "No date given".
- Rows are in date order.

## Output format

Use this structure so the student can scan it and copy rows into a calendar:

```
## [Course number] — [Course name], [Term Year]
Class meets: [days, time, room]

### Dated items
| Date | Time | Item | Counts for | Syllabus says |
|---|---|---|---|---|
| Tue Feb 3, 2026 | 9:00 AM (derived: due at start of class) | Problem Set 2 | Problem sets, 15% total | "Feb 3 – PS2 due" / "problem sets are due at the start of class" |

### Recurring rules
- [Item] — [rule] — "[quote]"

### No date given
- [Item] ([weight]) — [what the syllabus says, and any related session date] — "[quote]"

### Check with your professor
- [Conflict, error, or unclear point, and why it matters] — "[quote]"

**Totals:** [N] dated items · [N] rules · [N] with no date · [N] to check
```

Leave a section out only if it's truly empty, and say "None" rather than dropping it when the student might expect it (e.g. "No date given: None").

If the syllabus has useful non-graded dates (holidays, no-class days, purchase-by dates), you may add a short `### Other dates (not graded)` section after the main list. Keep them out of the Dated items table so the graded list stays clean.
