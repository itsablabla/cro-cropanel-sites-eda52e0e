# Guarantee signal inconsistent across pages — dev spec
Site: nomadinternet.com · Priority 6 · Medium · Effort: Low (0.5-2 days)

## Problem
Guarantee heading appears on some pages but not on plans page where commitment is made.

## Evidence (from the live site)
> h2: SHOP WITH CONFIDENCE
> h2: The Fastest Rural & On-the-Go Internet in the USA

## Current state
notes: Guarantee missing on plans page

## Required change
notes: Add guarantee near pricing and CTAs

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add guarantee near pricing and CTAs
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_guarantee_signal_inconsistent_across_pages` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
