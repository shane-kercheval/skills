# Make operations idempotent

Design a state-changing operation that will be rerun or retried (a script, job, deploy, or migration) so it reaches the correct end state no matter how many times it runs or where a previous run stopped.

**Why:** Scripts, jobs, deploys, and migrations crash, get retried, and get restarted. If leftover state changes the next run's outcome, every restart becomes a debugging session.

- Check what already exists before creating it.
- Compare by content, not by creation order or timestamps, which change from run to run.
- Clean up or adopt stale artifacts from a crashed run instead of failing on them.
- Make retries safe: the same request twice should not do the work twice.

**The test:**
1. What happens if this runs twice in a row?
2. What happens if the previous run crashed at any point?
3. Does rerunning converge to the same end state?

If any answer is "it depends on what state was left behind", the operation needs a step that reconciles existing state first.
