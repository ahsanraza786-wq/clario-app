# Increment 2 — Polish & robustness pass

Status: FINALIZED · Built under Clario Operating Model v1.0

## Usability audit (issues found)
- Overview stat tiles were not clickable (dead ends).
- Logo did not return to the home page.
- Create-a-policy had no formatter and showed plain monospace text, not a formatted document.
- Documents rows did not open a preview.
- To-Do items did not open the related rule/action.
- Rule-drawer "Edit" only showed a toast ("Sent for edits") instead of letting the user edit; "Approve" gave weak feedback.

## Fixes (Develop)
- Overview stat tiles are now clickable with hover affordance → jump to Frameworks / To-Do.
- Logo is clickable → returns to Overview.
- Create-a-policy now renders a properly formatted document (headings, sections) with a formatting toolbar: Bold, Italic, Underline, Bullet list, an Edit toggle (inline editing), Copy, and Download (.doc).
- Documents rows open a formatted preview in a modal.
- To-Do items open the related rule detail.
- Rule-drawer "Edit" now makes the draft inline-editable (Edit → Done); "Approve" confirms and closes cleanly ("saved to Documents & Audit Pack").
- Added clear click affordances (cursor, hover, arrows) to interactive rows.

## Test & QA
- JavaScript validated with `node --check` (passes).
- Verified: tiles navigate; logo returns home; policy formatting toolbar works (bold/italic/underline/list, edit, copy, download); document previews open; to-do items open rules; rule draft edits inline and approves cleanly.

## Definition of Done — met
Works (happy path + edge) · design standards · documented · validated · no secrets/data exposed.

## Follow-ups
- Progressive icon migration across remaining screens.
- Make the AI genuinely live (Claude drafting agent — needs API key + server function).
