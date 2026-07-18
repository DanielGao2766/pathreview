## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/52

**Issue title:** Add a contribution_streak field to the GitHub analysis (longest consecutive days of commits)
 
**Tier:**  Tier 2

**Problem summary:**
The current GitHub analysis reports information about a user's GitHub activity, but it does not measure contribution consistency over time. Because this metric is absent, users cannot easily demonstrate one aspect of sustained engagement with open-source projects. Consistent contribution activity is often viewed as a positive portfolio signal, so the analysis is missing information that could better represent a developer's coding habits.

A successful fix would add a new contribution_streak field to the GitHub analysis. This feature would calculate the longest sequence of consecutive days containing commits, and include that value in the analysis results so it can be displayed or used alongside the existing GitHub metrics.

I selected this issue because it is a well-scoped feature with a clear objective and a limited impact area. The work is on extending an existing feature by adding one additional tool that will display one additional metric rather than creating a new feature or redesigning an exisiting one. This fits in well with honing my skills of understanding existing code and integrating my code with the pre-existing test suite.

**Branch name:** (https://github.com/DanielGao2766/pathreview/tree/feat/52-contribution-streak-tool)

**Setup confirmation:** App runs locally at localhost:5173

**Cohort ledger:** Issue added to cohort ledger