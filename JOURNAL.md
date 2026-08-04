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
Implemented `_longest_contribution_streak` in `agent/tools/github_tool.py` (replacing the stub from Week 8) and wired it into `_fetch_repo_metadata` as a new `contribution_streak` field. Switched the data source from the originally planned single-repo REST commits endpoint to GitHub's GraphQL `contributionsCollection` API, since account-wide streak (not repo-scoped) is the intended semantics per the issue. Added `tests/unit/test_github_tool.py` covering all edge cases from PLAN.md (no token, zero contributions, single day, unbroken streak, gap in the middle, same-day duplicate commits, nonexistent user, request failures, and integration into `_fetch_repo_metadata`).

**Next steps:**
Run `make check` and `make test-unit`, confirm no new failures vs. baseline, then open the PR and request review.

**Blockers:**
None.


---

### Check-in 2 (end of week)

**PR link:** (https://github.com/ascherj/pathreview/pull/839)

**Branch:** feat/52-contribution-streak-tool

**What you built:**
Added a `contribution_streak` field to GitHub analysis output that reports the longest run of consecutive days with GitHub activity for a user's account, computed via GitHub's GraphQL `contributionsCollection` API. The field is now included in the dict returned by `GitHubTool.execute()` alongside existing repo metadata.

**Tests added or updated:**
Added `tests/unit/test_github_tool.py` (new file, 9 tests). Covers: no API token (bails out without a request), zero contributions, a single contribution day, an unbroken streak, a streak with a gap in the middle (verifies longest-run logic, not total days or most-recent run), multiple contributions on the same day collapsing to one day, a nonexistent user, an exception during the request, and that the field is correctly wired into `_fetch_repo_metadata`'s output.

**Self-review confirmation:** [x] make check passes  [x] make test-unit passes

**Draft PR feedback received from:** 
None
