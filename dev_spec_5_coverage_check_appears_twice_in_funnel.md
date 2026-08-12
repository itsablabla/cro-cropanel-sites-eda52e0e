# Coverage check appears twice in funnel — dev spec
Site: nomadinternet.com · Priority 5 · Medium · Effort: Medium (2-5 days)

## Problem
Coverage check CTA appears on both homepage and plans page, forcing users to repeat a step.

## Evidence (from the live site)
> ctas: CHECK COVERAGE | CHECK IF IT WORKS AT MY ADDRESS | SEE MY OPTIONS | GET STARTED | START CHAT | SEE WHAT I QUALIFY FOR | CHECK MY COVERAGE
> ctas: CHECK COVERAGE | SEE WHAT I QUALIFY FOR | CHECK MY COVERAGE

## Current state
cta: CHECK COVERAGE on both pages; notes: Redundant coverage check

## Required change
cta: Remove redundant coverage check from plans page; notes: Carry result forward

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Carry result forward
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_coverage_check_appears_twice_in_funnel` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 1,941,808 visitors per variant to detect a 2.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
