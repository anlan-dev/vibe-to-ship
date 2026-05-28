# /plan Command

**Purpose**: Create a detailed implementation plan before writing any code.

**When to use**: Before starting any new feature, major change, or complex task.

**How it works**:

1. Restate the requirement clearly
2. Identify risks and dependencies
3. Create a phased implementation plan
4. Wait for user confirmation before proceeding

## Usage

```
/plan Add user authentication with email and password
```

## What Happens

The AI will:

1. **Analyze the request** and restate it in clear terms
2. **Break it into phases** with specific, actionable steps
3. **Identify dependencies** between components
4. **Assess risks** and potential blockers
5. **Estimate complexity** (simple / medium / complex)
6. **Present the plan** and wait for explicit confirmation

## Example

```
User: /plan Add habit streak tracking with weekly stats

AI (planner):

# Implementation Plan: Habit Streak Tracking

## Overview
Add streak calculation and weekly statistics to the habit tracker.
Users will see their current streak, best streak, and weekly completion rate.

## Requirements
- Calculate current consecutive-day streak
- Track best-ever streak
- Show weekly completion percentage
- Display on habit detail page

## Implementation Steps

### Phase 1: Data Layer
1. Add streak calculation function (utils/streak.ts)
2. Add weekly stats function (utils/stats.ts)
3. Write unit tests for both functions

### Phase 2: UI Layer
4. Create StreakCard component
5. Create WeeklyStats component
6. Add to habit detail page

### Phase 3: Polish
7. Add empty state for new habits
8. Add loading state
9. Test responsive layout

## Complexity: Simple
## Estimated effort: 2-3 hours

**Waiting for confirmation**: Proceed with this plan? (yes/no/modify)
```

## Important

The AI will NOT write any code until you explicitly confirm the plan with "yes", "proceed", or similar.

To modify the plan:
- `modify: [your changes]`
- `different approach: [alternative]`
- `skip phase 2 and do phase 3 first`
