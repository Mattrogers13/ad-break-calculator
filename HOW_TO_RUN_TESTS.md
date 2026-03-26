# How to Run Claude Code Tests

## Files You Need

1. **ad-break-calculator.html** — Your web app
2. **CLAUDE_CODE_TEST_PROMPT.md** — This test plan (12 sections)

Both are in `/sessions/stoic-lucid-curie/mnt/outputs/`

## Option 1: Command Line (Fastest)

```bash
claude code CLAUDE_CODE_TEST_PROMPT.md ad-break-calculator.html
```

Replace with actual paths if needed.

## Option 2: Copy-Paste Method

1. Open Claude Code
2. Copy the contents of `CLAUDE_CODE_TEST_PROMPT.md`
3. Paste into Claude Code
4. Add: "Use the file at `/sessions/stoic-lucid-curie/mnt/outputs/ad-break-calculator.html`"
5. Let it run

## What Claude Code Will Do

- Open your HTML in Chrome automatically
- Click buttons, fill forms, and test features
- Take screenshots of each section
- Read the browser console for errors
- Check if timecodes display correctly
- Verify all 12 test sections pass or fail
- Generate a comprehensive report

## Expected Output

Claude Code will return:
- ✅ Which sections passed
- ❌ Which sections failed
- Screenshots of key moments
- List of bugs/issues found
- Clear "Ready for GitHub? YES/NO"

## Time Estimate

**~15-20 minutes** for full automated test run

## What to Do Next

**If tests PASS:**
- Push to GitHub (instructions in PROJECT_BRIEF_FOR_CLAUDE_CODE.md)

**If tests FAIL:**
- Review the issues Claude Code found
- Come back to me with the report
- I'll fix the problems
- Run tests again

---

## Need Help?

If Claude Code encounters issues:
1. Check that the HTML file path is correct
2. Ensure Chrome is installed (Claude Code uses Chrome for testing)
3. Make sure no other Chrome windows are using the profile
4. If stuck, share the error message and I'll help troubleshoot

---

That's it! Run Claude Code and let it test your app automatically.
