# LearningBridge — prototype quality report

Al Ahly · Milestone 3 · 14 November 2026

## Scope and continuity

Implemented the interactive-prototype requirement as a dependency-free web application. This continues the Grades 1–5 concept in Milestone 1 and the student upload, teacher verification and teacher support tasks in Milestone 2. Reem is the teacher and Ahmed is the Grade 4 demonstration student. Anonymous question-by-question review, a model-answer guide, concept history and teacher follow-up reflect the supplied interview findings. The earlier low-fidelity PDF and Figma file remain unchanged; this application is the high-fidelity deliverable.

## Mandatory coverage

| Requirement | Where to demonstrate it | Status |
| --- | --- | --- |
| Student entry and dashboard | Choose student; home shows recent results, pending work, skills and messages | Implemented |
| Scanned exam upload | Upload exam: PNG/JPG/PDF selection, camera input, drag/drop, preview, remove, reorder, readability check | Implemented |
| English/German exam workflow | Exam-language selector; sample paper and extracted answers; separate interface-language selector | Implemented |
| Status and confirmation | Submission timeline: extraction, verification, grading, approval, publication | Implemented |
| Teacher dashboard and queue | Class overview and Review queue; dates, status, search and filters | Implemented |
| Anonymous marking | Queue identity toggle; anonymous IDs during review | Implemented |
| Original beside OCR | Open review; source paper and editable extracted answer, per-question verification | Implemented |
| OCR verification before grading | Grading is disabled until all three answers are checked and nonempty | Implemented |
| Proposed grades and overrides | Per-question rubric, suggestion, teacher mark and feedback; bounds validation | Implemented |
| Teacher confirmation | Marks confirmed before support review; publication separately confirmed | Implemented |
| Learning gaps and red flags | Evidence-to-Practice Card compares two checked exams and explains suggested support | Implemented as labelled simulation |
| Confirm/dismiss flags | Teacher chooses a decision and gives a reason; suggestion is never automatically final | Implemented |
| Personalised feedback | Editable feedback and practice, follow-up date, preview and publication | Implemented |
| Final student result | Published score, question marks, checked answers, explanation and next practice | Implemented |
| Progress and historical results | Student progress/results; teacher student history and topic charts | Implemented |
| Teacher notifications | Publication, replacement request, comments and practice-review messages | Implemented |
| Full connected journey | Upload in student role → review in teacher role → publish → return to student | Implemented in the same browser |
| Responsive layouts | Desktop columns; phone stacking, horizontal teacher tables and student result cards | Implemented and sampled at 390px |

The queue shows the student name when anonymous mode is off. Mathematics is the selected demonstration subject; the header identifies the subject throughout the teacher workspace. Support is expressed constructively to the child instead of showing an alarming “at-risk” label.

## Unique contribution: Evidence-to-Practice

After confirming marks, open Learning support. The card presents the earlier Fractions 1 Q2 evidence beside the newly verified Fractions 2 Q2 answer and teacher mark. Confirm or dismiss extra support with a reason, edit a practice recommendation, set a follow-up date and publish. Ahmed can complete the fraction-strip exercise. Reem then reads the response, gives feedback and completes or continues the follow-up in Student progress. This demonstrates the full evidence → decision → practice → review loop, rather than an isolated warning.

## Additional implemented interactions

- Clearer-page request and replacement upload.
- Simulated connection failure with retained files and retry.
- Reopening OCR invalidates dependent approvals and hides the pending result.
- Editable/importable plain-text marking guide.
- Local persistence of decisions and uploaded originals after reload.
- Student help requests and teacher comments.
- Approved-results CSV export, audit history, demo guide and reset.
- Keyboard focus styles, labelled fields, skip navigation, status text alongside colour, reduced-motion support and semantic dialogs.

## Verification actually performed

Automated domain checks passed for workflow gates, mark bounds, score overrides, publication, approval invalidation, replacement and the no-current-gap case. JavaScript syntax checks passed.

Chrome browser automation passed 22 checks. These included:

1. Student dashboard rendering; empty/unsupported upload validation.
2. Sample preview, interrupted-upload recovery and successful submission.
3. Queue identity toggle; disabled grading before verification.
4. Correcting OCR, checking answers and generating simulated grades.
5. Rejection of an out-of-range mark; answer-key text import; live total update.
6. Score override from 7/10 to 8/10, support decision and publication gates.
7. Student preview and published result matching the teacher's 8/10 and edited feedback; private note absent.
8. Notification read/open, practice submission, teacher reply and completion.
9. CSV download.
10. Reopening verification hides the pending grade and resets approval.
11. Clearer-page request, actual PNG preview/upload and replacement.
12. Reload preserving state and the uploaded original through IndexedDB.
13. Dismissing support without displaying confirmed-support messaging to the student.
14. German interface and German exam paper; previous result retained.
15. Student and teacher pages at 390px without horizontal page overflow.
16. No uncaught browser errors across that sequence.

These are grouped summaries of the 22 recorded checks, not additional test counts. `verification/browser-results.json` contains the individual results. Selected desktop and phone screenshots were visually reviewed, including the Evidence-to-Practice screen and mobile student home.

## Limits

- OCR, proposed grades, feedback and gap detection use labelled mock data with a fixed three-question fractions rubric. They do not analyse arbitrary uploaded papers.
- Role selection is for demonstration. There is no real authentication or protected server database. Teacher-private notes are excluded from the student interface, not secured from someone inspecting browser storage.
- Both roles must use the same browser/site origin. A second device or a private browsing session starts a separate demo.
- Ahmed has the complete live journey. Lina and Omar are labelled historical background records. The demonstration covers mathematics; it is not a full school administration system.
- Attendance/missed-assignment inputs, calendar booking and parent access are not implemented. These optional extensions are outside the assessed core upload-to-feedback workflow.
- English/German exam and interface support is present; teacher-written feedback is not automatically translated, and some demonstration/audit labels remain English.
- File selection and image preview were tested in Chrome. PDF upload/preview and native mobile camera support are implemented but were not exercised on a physical phone or independently tested across browsers.
- Responsive browser checks do not establish usability for children. No new teacher/child usability study, screen-reader audit or formal accessibility certification has been performed.

## Before submitting the complete milestone

This is the completed interactive-prototype component. Also provide the required 2–4 minute walkthrough, HTDs for the same three Milestone 2 tasks, and the required conversation/prompt history. The supplied README includes local run instructions and a demonstration sequence. Supply the coded source/repository as required by the submission form. A private hosted preview is owner-only: verify TA access before relying on that URL, or provide the source package and run instructions. Use the sample exam and reset the demo before recording.
