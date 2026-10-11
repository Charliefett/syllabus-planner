# Syllabus Planner

A free Claude skill that turns one course syllabus into a complete list of every graded item and its due date. Each date comes with the exact syllabus line it came from, so you can check it in seconds.

## What it does

Give Claude a syllabus (PDF, Word file, or pasted text). You get back:

- **Dated items**: every homework, quiz, exam, project and graded session with a date, in date order, with the time when the syllabus states or implies one.
- **Recurring rules**: deadlines written as rules (for example, "due Friday at noon the week after release"), stated once instead of turned into guessed dates.
- **No date given**: graded items the syllabus never dates, so nothing that counts toward your grade is left off.
- **Check with your professor**: contradictions or errors in the syllabus, such as a date on the wrong weekday or two different weights for the same assignment.

What it will not do:

- **Invent dates.** If the syllabus doesn't give a date, the list says so.
- **Change your calendar.** It doesn't add to your calendar or set reminders. You copy the dates where you want them.
- **Need extras.** It works without connectors or internet access.

## Example (fictional syllabus)

| Date | Time | Item | Counts for | Syllabus says |
|---|---|---|---|---|
| Tue Feb 3, 2026 | 9:00 AM (derived: due at start of class) | Problem Set 2 | Problem sets, 15% total | "Feb 3 – PS2 due" / "problem sets are due at the start of class" |
| Thu Mar 5, 2026 | In class, 9:00–10:15 AM | Midterm | Exams, 25% | "Mar 5 – Midterm (in class)" |

## Install (Claude Free, Pro or Max)

1. In Claude, go to **Settings > Capabilities** and turn on **Code execution and file creation**. Skills need it, and they appear greyed out without it.
2. Download **[`syllabus-planner.zip`](syllabus-planner.zip)** from this repository: open the file, then click the download button.
3. In Claude, go to **Customize > Skills**, click **+**, then **+ Create skill**, then **Upload a skill**, and choose the ZIP you downloaded.
4. Make sure **syllabus-planner** is switched on in your skills list.

Use the ZIP file above, not GitHub's green **Code > Download ZIP** button. That button adds `-main` to the folder name, and Claude rejects a skill whose folder name doesn't match the skill name.

Official instructions: [Use skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

## Use

Start a chat, attach your syllabus and ask something like:

> Here's my syllabus. Make me a list of everything that's due this semester.

Run one syllabus per request. For several classes, send them one at a time.

## How it was tested

The skill was tested on three real university syllabi: a dense weekly schedule, one with no dated deadlines at all, and one with errors in it. Its output was compared against an answer key built separately. Each syllabus was run three times:

- **Dated items:** all 68 found, every run.
- **Invented dates:** none.
- **Syllabus errors:** the date and grade-weight errors in those syllabi were flagged every run.

Without the skill, Claude found the same dates on the dense schedule. On the syllabus with no dates, it produced 13 guessed Friday deadlines that were not in the syllabus.

Three syllabi is a small sample. Always check the dates against your syllabus and your course site, because professors change schedules.

## License

MIT. See [LICENSE](LICENSE).

## Author

Designed and tested by [Charlie Fett](https://github.com/charliefett). Written with Claude.
