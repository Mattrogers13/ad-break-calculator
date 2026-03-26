# Ad Break Calculator - Claude Code Testing Brief

## Task
Automatically test the ad-break-calculator.html web app using browser automation. Open the file in Chrome, execute the test plan below, and generate a detailed test report.

## File Location
- **HTML File:** `/sessions/stoic-lucid-curie/mnt/outputs/ad-break-calculator.html`
- **Test Plan:** Sections 1-11 below

---

## SECTION 1: Initial Load & Interface

**Action:** Open the HTML file in Chrome using `file://` protocol.

**Verify:**
- [ ] Page loads without errors (check console for errors)
- [ ] Header displays "Ad Break Calculator"
- [ ] Controls section visible with "Show Duration" input field
- [ ] Input field has placeholder "01:00:00;00"
- [ ] Current value shows "01:00:00;00"
- [ ] Strategy dropdown visible with "Redistribute", "Snap", "Preserve" options
- [ ] Four buttons visible: "Auto-Suggest", "↶ Undo", "↷ Redo", "Reset"
- [ ] Timeline section present with visual bar
- [ ] Summary section present with stats
- [ ] Break cards grid visible below

**Report:** Pass/Fail with screenshot

---

## SECTION 2: Input Field Functionality

**Action 1:** Click the "Show Duration" input field.

**Verify:**
- [ ] Field is focusable and cursor appears
- [ ] Field is not read-only
- [ ] Can type into field

**Action 2:** Clear the field and type `00:30:00;00`

**Verify:**
- [ ] Text appears in field correctly
- [ ] No validation errors block input
- [ ] Field accepts the timecode

**Action 3:** Press Enter/Tab to confirm

**Verify:**
- [ ] Timeline updates to show new duration
- [ ] Timeline info shows "00:00:00;00 — 00:30:00;00"

**Report:** Pass/Fail with screenshots of before/after

---

## SECTION 3: Auto-Suggest Button (Redistribute Strategy)

**Precondition:** Duration is set to `00:30:00;00`

**Action 1:** Ensure "Redistribute Evenly" is selected in Strategy dropdown

**Action 2:** Click "Auto-Suggest" button

**Verify:**
- [ ] Button is clickable
- [ ] At least 5 break cards appear below (B1, B2, B3, B4, B5)
- [ ] Each break card has:
  - [ ] Break number (B1, B2, etc.)
  - [ ] Lock icon (🔓)
  - [ ] Timecode input field
  - [ ] Copy button (📋)
  - [ ] Spacing badge showing timing info
- [ ] All breaks have timecodes filled in (not "—")
- [ ] Timecodes are in HH:MM:SS;FF format
- [ ] Breaks are distributed across the 30-minute show
- [ ] Summary shows "Placed: 5", "Valid: 5"
- [ ] Timeline shows 5 green markers (valid breaks)
- [ ] "All Valid" badge is green

**Report:** Pass/Fail with screenshots of break cards and timeline

---

## SECTION 4: Lock/Unlock Functionality

**Precondition:** 5 breaks are placed from Section 3

**Action 1:** Click the lock button (🔓) on Break #2

**Verify:**
- [ ] Icon changes to 🔒
- [ ] Lock button background turns blue

**Action 2:** Click "Auto-Suggest" again with Redistribute selected

**Verify:**
- [ ] Break #2 timecode stays the same (locked position preserved)
- [ ] Other breaks redistribute around the locked break #2
- [ ] Summary still shows 5 valid breaks

**Action 3:** Click lock button on Break #2 again

**Verify:**
- [ ] Icon changes back to 🔓
- [ ] Lock button background returns to normal

**Report:** Pass/Fail with descriptions of lock state changes

---

## SECTION 5: Manual Timecode Input

**Precondition:** Breaks are placed

**Action 1:** Click timecode input field on Break #1

**Action 2:** Clear field and type `00:05:00;00`

**Action 3:** Press Enter

**Verify:**
- [ ] Field accepts input
- [ ] Break #1 timecode updates to `00:05:00;00`
- [ ] Spacing badge updates
- [ ] Summary "Last Break" updates if applicable
- [ ] Card border color updates (green if valid, red if invalid)

**Report:** Pass/Fail with screenshot

---

## SECTION 6: Copy to Clipboard

**Precondition:** Break #1 has timecode `00:05:00;00`

**Action:** Click the copy button (📋) on Break #1

**Verify:**
- [ ] Button is clickable
- [ ] No error appears
- [ ] Timecode is copied to clipboard (manual verification: paste into another field)

**Report:** Pass/Fail (or manual paste verification)

---

## SECTION 7: Undo/Redo Functionality

**Precondition:** You've made changes (placed breaks, locked/unlocked, entered timecodes)

**Action 1:** Click "↶ Undo" button

**Verify:**
- [ ] Previous state is restored
- [ ] Duration input might change back
- [ ] Break positions revert

**Action 2:** Click "↷ Redo" button

**Verify:**
- [ ] Forward state is restored
- [ ] Changes reappear

**Action 3:** Test keyboard shortcut Ctrl+Z

**Verify:**
- [ ] Undo works via keyboard

**Action 4:** Test keyboard shortcut Ctrl+Y

**Verify:**
- [ ] Redo works via keyboard

**Report:** Pass/Fail for each undo/redo action

---

## SECTION 8: All Three Strategies

**Action 1: Snap Strategy**
- Set duration to `00:30:00;00`
- Select "Snap to Valid" from dropdown
- Click "Auto-Suggest"

**Verify:**
- [ ] Breaks are placed
- [ ] Breaks snap to valid positions (spacing is 6-10 minutes)

**Action 2: Preserve Strategy**
- Lock Break #2 at current position
- Select "Preserve Position" from dropdown
- Click "Auto-Suggest"

**Verify:**
- [ ] Break #2 stays locked
- [ ] Other breaks fill gaps around it
- [ ] All breaks valid if possible

**Report:** Pass/Fail for each strategy

---

## SECTION 9: Reset Button

**Precondition:** Breaks are placed and configured

**Action:** Click "Reset" button

**Verify:**
- [ ] All break timecodes cleared (show "—")
- [ ] All lock icons reset to 🔓
- [ ] Duration input resets to `01:00:00;00`
- [ ] Summary shows "Placed: 0", "Valid: 0"
- [ ] Break cards remain visible but empty

**Report:** Pass/Fail with screenshot

---

## SECTION 10: Validation Visual Feedback

**Action:** Place breaks with invalid spacing (less than 6 min apart)

**Verify:**
- [ ] Card borders turn RED for invalid breaks
- [ ] Spacing badge shows "✗" instead of "✓"
- [ ] "All Valid" badge turns red and shows "Issues Found"
- [ ] Cards with valid breaks show GREEN border

**Report:** Pass/Fail with color screenshots

---

## SECTION 11: Summary Stats Update

**Precondition:** Multiple breaks placed

**Action:** Watch summary section as you modify breaks

**Verify:**
- [ ] "Placed" count updates immediately
- [ ] "Valid" count updates when validity changes
- [ ] "Avg Spacing" shows correct timing
- [ ] "Last Break" shows the last placed break timecode

**Report:** Pass/Fail with example stats

---

## SECTION 12: Console & Error Check

**Action:** Open Chrome DevTools (F12) and check Console tab

**Verify:**
- [ ] No JavaScript errors
- [ ] No console.error messages
- [ ] No warnings about missing elements

**Report:** Pass/Fail with screenshot of clean console

---

## Final Report

When all sections complete, provide:

**Test Summary:**
- Total sections: 12
- Sections passed: __
- Sections failed: __
- Critical issues: (list any blocking bugs)
- Minor issues: (list any cosmetic/UX issues)

**Blocking Issues:** (if any)
- Issue 1: [description]
- Issue 2: [description]

**Cosmetic/Non-Blocking Issues:** (if any)
- Issue 1: [description]

**Ready for GitHub?** YES / NO
- If NO, list what needs to be fixed

**Recommendation:**
[Your assessment on whether the app is ready to push to GitHub]

---

## How to Execute This

1. Save this file
2. Run: `claude code <path-to-this-file> <path-to-html-file>`
3. Or paste both the HTML file path and this test plan into a Claude Code session
4. Let Claude Code execute the tests autonomously
5. Review the final test report

Claude Code will open your HTML in Chrome, click through all tests, take screenshots, and give you a detailed pass/fail report.
