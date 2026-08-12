# Social proof absent on plans page — dev spec
Site: nomadinternet.com · Priority 4 · High · Effort: Medium (2-5 days)

## Problem
Plans page lacks testimonials that appear elsewhere, missing trust at decision point.

## Evidence (from the live site)
> h2: Real Stories from Real Users
> h2: Real Stories from Real Users

## Current state
notes: Testimonials missing on plans page

## Required change
notes: Add testimonials near pricing

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add testimonials near pricing
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_social_proof_absent_on_plans_page` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
