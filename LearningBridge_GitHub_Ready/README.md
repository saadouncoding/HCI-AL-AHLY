# LearningBridge — Milestone 3

Al Ahly · CSEN 909 · German University in Cairo

A high-fidelity interactive continuation of the Grades 1–5 assessment concept, Reem's teacher workflow and Ahmed's Grade 4 demonstration. The distinctive Evidence-to-Practice Card links checked cross-exam evidence to a teacher decision, personalised practice and a reviewed follow-up.

## Run locally

Requires Node.js 18 or newer. No dependencies, installation, API keys or accounts are needed.

1. Open a terminal in this folder.
2. Run `npm start` (or `node serve.cjs`).
3. Open `http://127.0.0.1:4173` in Chrome, Edge, Safari or Firefox.

Alternatively: `python3 -m http.server 4173 --bind 127.0.0.1 --directory dist`.
Do not open index.html directly as a file: JavaScript modules need HTTP.
If port 4173 is occupied, use `PORT=4174 node serve.cjs` (macOS/Linux).

## Demonstrate the complete journey

1. Choose **I'm a student**. Open **Upload exam**. Choose English or German. Click **Use a sample exam**, preview it, confirm readability and **Send exam**.
2. The status shows simulated extraction, then waiting for teacher verification. Use the top-right role switch and select **I'm a teacher**.
3. Open **Review queue**. Anonymous IDs are on by default; turn them off to show Ahmed's name. Open the exam.
4. Check Q1. On Q2, correct `1/3 > 1/9` to `1/3 > 1/4`, then check it. Check Q3. **Confirm text & generate grades**.
5. Inspect the rubric and proposed marks. Change Q2 from 1 to 2 to demonstrate an override; the total becomes **8/10**. Edit its feedback. Confirm marks.
6. Inspect the two exam references in the **Evidence-to-Practice Card**. Confirm or dismiss support, enter a reason, review feedback and practice, and choose a follow-up date. Preview the student result, then publish and confirm.
7. Switch to the student result. The total is **8/10**, matching the teacher's edit. Messages contain a new notification. Open practice, use the fraction strips and submit an explanation.
8. Teacher → **Student progress** → Ahmed. Read the practice response, reply and mark the follow-up complete or continue practice. The student receives the reply.

The default suggested marks are 3/3, 1/3 and 3/4 = **7/10**. The illustrative 72% in the course brief is an example, not a required fixed grade. This follows the 10-point fractions demonstration in the prior wireframes.

## Other paths

- Upload actual PNG, JPG or PDF files, preview/remove/reorder them, or use camera capture on a supported mobile device.
- Upload panel → Demonstration options → simulate one connection failure. Files remain selected for retry.
- Teacher verification → request clearer page; student receives a replacement request and can resubmit.
- Reopen verification after publication: dependent approvals are reset and the pending result is hidden until reapproved.
- Change the answer key for an individual question or import a plain-text marking guide.
- Search/filter the review queue; inspect topic results and student histories; export approved results as CSV.
- Send a student help request or a teacher comment. These are in-app messages, not emails.
- Reset demo in the sidebar (or entry screen) restores the initial fictional records.

## What is real, and what is simulated

The interactions, state transitions, file previews, teacher edits, final totals, notifications, practice submissions and exports are functional. OCR, AI grades and gap recommendations are explicitly simulated against a fixed three-question fractions rubric. Uploading a different paper does not run real OCR; teachers can manually correct the extracted fields. No model accuracy is claimed.

State uses localStorage and uploaded files use IndexedDB. Both roles share the **same browser and site origin**, including across reloads. Different devices/browsers do not share state. This is demo role selection, not secure authentication or authorisation. Use sample files only; do not upload real pupil data. A reset clears stored demo files and decisions.

English and German exam examples and interface labels are provided. Original exam text is never overwritten by an interface language change. Teacher-authored comments keep the language in which they were written; they are not auto-translated. The English rubric text can be edited/imported by the teacher. Some demonstration labels and audit entries remain English.

Lina and Omar are read-only fictional background records; the complete live workflow is Ahmed's. Parent access, real email/calendar delivery, real AI and server synchronisation are outside this prototype. The browser camera control depends on device support.

## Checks

`npm test` checks workflow gates, bounds, score overrides, publication, approval invalidation, replacement and current-gap logic.
`npm run check` checks JavaScript syntax.
See `QUALITY_REPORT.md` for the browser interactions actually tested and known limits. No child usability study or accessibility certification is claimed.

## Files

- `dist/index.html`, `styles.css`: responsive interface and design system.
- `dist/app.js`: screens, interactions, persistence and file handling.
- `dist/model.js`: assessment state machine and approval rules.
- `serve.cjs`: dependency-free local preview server.
- `tests/model.test.mjs`: domain-rule checks.

## Submission

This deliverable covers the interactive prototype. The course's complete Milestone 3 also asks for a **2–4 minute walkthrough video**, **HTDs for the same three Milestone 2 tasks**, and a repository link/run instructions if coded. Include the required conversation/prompt history. The supplied demo guide helps you record the walkthrough; it is not the video itself. Check the course form and any shared-link permissions before submitting. A private hosted preview cannot be assumed accessible to the TA.
