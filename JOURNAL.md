## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/52

**Issue title:** Add a contribution_streak field to the GitHub analysis (longest consecutive days of commits)
 
**Tier:** Tier 2

**Problem summary:**
The current GitHub analysis reports information about a user's GitHub activity, but it does not measure contribution consistency over time. Because this metric is absent, users cannot easily demonstrate one aspect of sustained engagement with open-source projects. Consistent contribution activity is often viewed as a positive portfolio signal, so the analysis is missing information that could better represent a developer's coding habits.

A successful fix would add a new contribution_streak field to the GitHub analysis. This feature would calculate the longest sequence of consecutive days containing commits, and include that value in the analysis results so it can be displayed or used alongside the existing GitHub metrics.

I selected this issue because it is a well-scoped feature with a clear objective and a limited impact area. The work is on extending an existing feature by adding one additional tool that will display one additional metric rather than creating a new feature or redesigning an exisiting one. This fits in well with honing my skills of understanding existing code and integrating my code with the pre-existing test suite.

**Branch name:** (https://github.com/DanielGao2766/pathreview/tree/feat/52-contribution-streak-tool)

**Setup confirmation:** App runs locally at localhost:5173

**Cohort ledger:** Issue added to cohort ledger

## Week 8 — Reproduction & solution planning

**Reproduction commit link:** https://github.com/ascherj/pathreview/commit/2152eb9c36d3de8cd5a43204a205afd6cf5b6838

**Reproduction summary:**
I located the gap in the feature within the agent/tools folder where I found github_tool.py. Since I could not find a method that calculates the longest commit streak of a user based on their github profile, I added a method stub that I will be implementing through the plan in the PLAN.md

**PLAN.md link:** (https://github.com/DanielGao2766/pathreview/blob/feat/52-contribution-streak-tool/PLAN.md)

**Blockers or open questions:**

## Week 9 — Solution building & PR submission

### Check-in 1 (mid-week)

**Current progress:**
[What have you implemented so far? Which sub-tasks from PLAN.md are done?]

**Next steps:**
[What are you working on for the rest of the week?]

**Blockers:**
[Anything slowing you down? Or leave blank.]

---

### Check-in 2 (end of week)

**PR link:** [link to your submitted pull request]

**Branch:** [the branch name you worked on, e.g. `fix/123-short-description`]

**What you built:**
[1–3 sentences summarizing what your fix does and how it works]

**Tests added or updated:**
[Which test files did you touch? What do they cover?]

**Self-review confirmation:** [ ] make check passes  [ ] make test-unit passes

**Draft PR feedback received from:** [name or Slack handle, or "none"]
