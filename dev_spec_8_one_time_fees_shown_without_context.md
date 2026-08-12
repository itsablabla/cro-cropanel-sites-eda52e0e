# One-time fees shown without context — dev spec
Site: nomadinternet.com · Priority 8 · Medium · Effort: Low (0.5-2 days)

## Problem
One-time fees listed without explanation, leaving total cost unclear.

## Evidence (from the live site)
> h2: $0.00 (one-time)
> h2: $99.99 (one-time)

## Current state
notes: One-time fees unexplained

## Required change
notes: Add labels explaining fees

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add labels explaining fees
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_one_time_fees_shown_without_context` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
