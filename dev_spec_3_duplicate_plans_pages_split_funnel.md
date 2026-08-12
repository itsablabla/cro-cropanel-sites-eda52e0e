# Duplicate plans pages split funnel — dev spec
Site: nomadinternet.com · Priority 3 · Urgent · Effort: Medium (2-5 days)

## Problem
Two URLs serve identical plans content, splitting the conversion path and confusing users about which is canonical.

## Evidence (from the live site)
> PAGE /pages/plans
> PAGE /plans
> h1: Let's Get You the Right Internet
> h2: The Fastest Rural & On-the-Go Internet in the USA

## Current state
h1: Let's Get You the Right Internet; notes: Two URLs with same content

## Required change
h1: Let's Get You the Right Internet; notes: Consolidate to one canonical URL and redirect the other

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Consolidate to one canonical URL and redirect the other
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_duplicate_plans_pages_split_funnel` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 124,891 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
