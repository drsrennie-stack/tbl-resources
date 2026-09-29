# Compliance Notes

## 1. Project

- Project: TBL Session Creator (Solano Community College, BIO 004 and BIO 005)
- Files covered: tbl-session-creator.html
- Date: September 29, 2026

## 2. WCAG version and level

Target: WCAG 2.2 AA minimum, AAA where achievable.

| Criterion | Level reached | Notes |
|---|---|---|
| 1.3.1 Info and relationships | AA | Semantic header, main, section, footer; labels tied to fields with for and id; competency list in a fieldset with a legend |
| 1.4.3 / 1.4.6 Text contrast | AAA | Every text pair is 7:1 or higher except placeholder text (6.5:1, above AA) |
| 1.4.11 Non-text contrast | AA | Field and checkbox-row borders 3.8:1 |
| 2.1.1 Keyboard | AA | All controls are native buttons, selects, inputs, checkboxes, and links |
| 2.4.1 Bypass blocks | A | Skip link to main content |
| 2.4.7 / 2.4.13 Focus visible and appearance | AA | 3px navy outline with 2px offset on every focusable element |
| 3.3.1 / 3.3.3 Error identification and suggestion | AA | Errors named in text, aria-invalid set, message linked with aria-describedby, focus moves to first problem, count announced |
| 4.1.2 Name, role, value | AA | Key terms toggle uses aria-expanded and aria-controls; platform chooser is a native modal dialog with a labeled heading, Esc to close, and a named close button |
| 4.1.3 Status messages | AA | Form status, copy status, and competency count use role="status" or aria-live |
| 2.3.3 Animation from interactions | AAA | prefers-reduced-motion turns off transitions, card lift, and smooth scrolling |

## 3. Color contrast audit

| Text / background | Ratio | Result |
|---|---|---|
| Navy #0B1530 on white | 18.04:1 | Pass AAA |
| Navy #0B1530 on off-white #FAFAF9 | 17.27:1 | Pass AAA |
| Navy #0B1530 on selected fill #EEF0F5 | 15.82:1 | Pass AAA |
| Terra #8B3A2E on white | 7.66:1 | Pass AAA |
| Terra #8B3A2E on off-white | 7.33:1 | Pass AAA |
| Terra-dark #6F2E24 on white | 10.04:1 | Pass AAA |
| Muted #404A5E on white | 8.90:1 | Pass AAA |
| Muted #404A5E on off-white | 8.52:1 | Pass AAA |
| White on terra #8B3A2E (primary button) | 7.66:1 | Pass AAA |
| White on navy #0B1530 (AI buttons, toast) | 18.04:1 | Pass AAA |
| Placeholder #555E71 on white | 6.51:1 | Pass AA (AAA for large text) |
| Control border #7A8397 on white | 3.80:1 | Pass 1.4.11 |
| Gold #C9A14A badge border | 2.42:1 | Decorative only, carries no information |

## 4. Keyboard navigation flow

Skip link, Show key terms, course select, module, topic, search, Select all shown, Clear selection, each competency checkbox, remove buttons on selected chips (focus moves to the next chip after removal), identity and objective fields, source options, RAT settings, application settings, peer evaluation, export options, Reset, Design my session prompt. After building, focus moves to the output card, then New answer key, Copy prompt, the prompt text (focusable for scrolling), the four AI links, the source links, and the footer link.

Checked with an automated headless browser run. The full sequence has not yet been walked by hand.

## 5. Screen reader testing

Not yet done with a real screen reader. Structure was built for it: required fields announced as required, progress bar reports "X of 15 required fields complete", errors are linked to their fields, competency tags are read as text, and the remove buttons are named "Remove [competency]". Recommended check: VoiceOver on macOS Safari and NVDA on Windows Firefox.

## 6. Known limitations and remediation

- Screen reader and hand keyboard testing still to be done (see sections 4 and 5).
- The competency list for a whole course is long (up to 268 items). The module and topic filters and search keep it usable, but a screen reader user tabbing through "All modules" will hear many items. Remediation: filter by module first, which the layout encourages.
- The printable HTML that the AI produces follows the stylesheet in the prompt, but each AI output should get its own contrast and structure check before students use it.

## 7. Reviewer

Built and automated checks by Claude. Final review: Dr. Sharilyn Rennie.
