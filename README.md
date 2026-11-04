# Doctolib check-in prototypes: Claude vs Figma Make

**Open the comparison: https://bfoldes.github.io/doctolib-comparison/**

Side-by-side screenshots of two versions of the same AI-timed appointment check-in prototype (AI Native course, Module 2):

- **Claude version:** https://bfoldes.github.io/doctolib-checkin-prototype/
- **Figma Make version:** https://sleet-vine-74175355.figma.site

Each pair shows the Claude version on the left and the Figma Make version on the right, with the state name above it.

## What we did

1. **Captured both prototypes with Playwright** (Python, driving Google Chrome), at a phone size of 390 × 844.
2. **Hid the state switcher** by adding `test` to every link, so the screenshots look like what testers see.
3. **Matched the same states in both versions:** lock screen (high confidence), high confidence, low confidence, no result, cold start, AI off and longest content.
4. **Captured the booking confirmation** after 4 seconds (waiting, then ready) and after 11 seconds (waiting, then failure). The waits are counted from when the page has finished loading.
5. **Clicked through from the high confidence card** in both versions: Check-in settings, Still works, Reschedule picker, Reschedule review, the cancel dialog, the cancelled card and Contact the practice.
6. **Built one comparison page** (`index.html`) and published it here with GitHub Pages.

## What couldn't be matched one to one

- **Check-in cards other than high confidence:** the Figma Make switcher only links these states to the lock screen, so the script opens the lock screen and taps the notification to get the card.
- **Reschedule review:** both show the review after tapping the first time slot, but the slots differ (Claude: Fri, 20 Nov, 8:00. Figma Make: Wed, 18 Nov, 09:00).
- **Only in Figma Make:** High confidence / no note, Ready and Failure as separate direct states, Waiting (long), a lock screen for every scenario, and the follow-up screens Rescheduled, Book again, Rebooked, Remind later, Timing submitted and Upcoming.
- **Only in Claude:** `#booking-long`, which matches Figma Make's "Waiting (long)" but wasn't part of the comparison.

## Notes

- The page is public for anyone with the link, but it asks search engines not to list it (`noindex`).
- All data in both prototypes is invented. This is a course prototype, not a Doctolib product.
- Only the page, this README and the screenshots are in this repo. The capture scripts stay local.
