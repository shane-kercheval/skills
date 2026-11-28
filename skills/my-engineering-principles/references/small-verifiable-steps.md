# Small verifiable steps

When work takes more than one change, break it into small steps that each end in a state you can check, and don't start the next step until the current one passes.

**Why:** A break caught at the step that caused it is cheap to find. A break found after a batch of changes is buried, and more work has been built on top of it.

- **Put foundations first.** If something helps every later step (test setup, shared types, a baseline measurement), do it before the features that depend on it.
- **In a sweep of similar edits,** check each change before making the next.
- **When the goal is to change a number or an existing behavior, capture a baseline first,** so the check reads "before versus after".
- **Order commits so they tell the story:** a failing test, then the fix; a removal, then the rebuild; setup, then the feature. Each commit should stand on its own, so a reviewer can read it, and anyone can revert it, without the others.

Related: [prove it works](prove-it-works.md), [script the work](script-the-work.md).
