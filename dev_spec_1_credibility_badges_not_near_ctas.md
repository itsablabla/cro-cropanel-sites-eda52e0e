# Credibility badges not near CTAs — dev spec
Site: nomadinternet.com · Priority 1 · Medium · Effort: Medium (2-5 days)

## Problem
Media logos appear only on homepage, not near CTAs on other pages.

## Evidence (from the live site)
> h2: As Featured In:
> ctas: CHECK COVERAGE | SEE WHAT I QUALIFY FOR | CHECK MY COVERAGE

## Current state
notes: Badges only on homepage

## Required change
notes: Place badges adjacent to CTAs on subpages

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Place badges adjacent to CTAs on subpages
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_credibility_badges_not_near_ctas` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
