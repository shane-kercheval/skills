# Redesign from first principles

When a new requirement doesn't fit the existing design, don't bolt it on. Ask what you would build if the requirement had been known from the start, and move toward that.

**Why:** A requirement bolted onto a design built for something else leaves special cases around it, and each one makes the next change harder.

- Read all the affected code and understand the current design first.
- Ask: "if we were writing this from scratch with this requirement, what would we build?"
- Carry the change through everything it touches: types, docs, examples, tests.
- Design the whole change, then deliver it in small verified steps (see [small verifiable steps](small-verifiable-steps.md)).

Balance this against [smallest change](smallest-change.md): redesign when the bolted-on version would leave the design harder to understand, not for every small addition.
