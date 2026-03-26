# Ad Break Calculator

A professional timecode placement tool for TV/streaming video production. Intelligently calculates and distributes advertisement breaks across video content while respecting industry-standard spacing constraints.

## Features

- **Three Placement Strategies:**
  - **Redistribute**: Evenly distribute breaks across the duration
  - **Snap**: Snap breaks to valid placement positions (6-10 min spacing)
  - **Preserve**: Maintain locked break positions while filling gaps

- **Smart Validation:** Real-time validation with visual feedback (green for valid, red for invalid)
- **Break Management:**
  - Lock/unlock individual breaks to preserve positions
  - Manual timecode adjustment with live validation
  - Copy timecode to clipboard

- **Complete History:** Full undo/redo functionality with keyboard shortcuts (Ctrl+Z, Ctrl+Y)
- **Summary Statistics:** Track placed breaks, valid count, average spacing, and last break position
- **Professional UI:** Dark theme with timeline visualization

## Getting Started

1. Open `ad-break-calculator.html` in a modern web browser
2. Enter your show duration (e.g., `00:30:00;00` for 30 minutes)
3. Select a placement strategy
4. Click "Auto-Suggest" to generate break timecodes
5. Adjust breaks manually as needed
6. Copy timecodes to your video editing software

## Input Format

All timecodes use **SMPTE timecode format: HH:MM:SS;FF**
- HH = Hours (00-23)
- MM = Minutes (00-59)
- SS = Seconds (00-59)
- FF = Frames (00-29 for 30fps, 00-24 for 25fps)

Example: `00:15:30;15` = 15 minutes, 30 seconds, 15 frames

## Placement Rules

- **Minimum Spacing:** Breaks must be at least 6 minutes apart
- **Maximum Spacing:** Breaks should not exceed 10 minutes apart
- **Edge Breaks:** First break cannot be within 2 minutes of start; last break cannot exceed content duration

## Technical Details

- Pure HTML/CSS/JavaScript (no dependencies)
- Runs entirely in the browser
- No server required
- Local state management with undo/redo history

## Browser Support

- Chrome (latest) ✅
- Firefox (latest) ✅
- Safari (latest) ✅
- Edge (latest) ✅

## Files

- `ad-break-calculator.html` - Main application
- `TEST_REPORT.md` - Comprehensive test results
- `README.md` - This file

## Version

Current Version: **1.0.0** (Production Release)

## Testing

All 12 test sections pass with 100% success rate. See `TEST_REPORT.md` for detailed testing results.

## License

Created for professional video production use.

## Support & Feedback

For issues, feature requests, or feedback, please open an issue on this repository.

---

**Made with precision for professional video breaks.** ⏱️
