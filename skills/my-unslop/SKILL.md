---
name: my-unslop
description: Edits or reviews text against the writing rules in the global instructions, removing AI-writing patterns (slogans, inflated wording, filler, hedging, forced structure) while keeping the meaning. Use when the user asks to unslop, de-slop, clean up, tighten, or edit a draft, to review text for AI-writing patterns, or says your own last reply or document didn't follow the writing rules.
license: MIT. Adapted from pstack by Lauren Tan. See sources/pstack-LICENSE.txt in the skills repo
metadata:
  source: "cursor/plugins pstack/skills/unslop @ 12d587d"
---

# Unslop

The rules live in your global instructions, under "How to write". This skill applies them to one text.

1. **Pick the text.** Use the text the user gave or named. If they named none, use your own last reply, or the document you last wrote. When it's your own, the user invoked this because the text broke the rules, so reread "How to write" before anything else.
2. **Scan it** for the two faults those rules open with, and for the mechanics. The forms that slip through most:
   - A phrase that makes the reader guess what it means. Ask what the writer would say if the reader asked "what do you mean?".
     - a slogan, an aphorism, a personified thing, a figurative verb, or an idiom the reader has to translate into what happens
     - a vague word ("a weak description"), or a word that makes the reader ask "why that word?"
     - a sentence that doesn't say the point: it leads up to the point with a story, describes it by its effect on someone, or takes one of the forms listed under "State each point directly"
     - "it", "this", or "one" where the reader needs the noun, and one thing called by several names
     - a fragment, a dropped article, an arrow chain, or a table cell where the reader needs the full sentence
     - a row of short sentences where one fact causes or explains the next
     - "never ... unless" where "only if" says the same thing
     - a list that reads as complete and is not
     - the present tense for something that is only proposed
   - Words that add nothing to what the reader understands or decides.
     - filler, chatbot phrases, stacked hedges, and closing summaries
     - inflated words, and "serves as" for "is"
     - "not just X, but Y" and forced groups of three
     - narration of the text itself or of routine steps the reader would assume ("this section covers", "I reread the file")
     - detail the reader would assume or won't use, such as the checks that passed before a commit
   - Mechanics: em dashes, curly quotes, emoji, bold that marks nothing essential, and a first sentence that is not the answer or the point.
3. **Rewrite only what the rules cover.** Replace a phrase that makes the reader guess with the thing it refers to. If the text is someone else's and you can't tell what the phrase refers to, say so and don't guess. Leave a sentence that is already clear, even where you could make it more exact. Keep the meaning and the intended tone, and don't add new points.
4. **Return the result.** If the user asked for an edit, or the text is your own, return the edited text. If they asked for a review, or the text is their own writing and they didn't ask you to change it, list each problem with its fix and leave the wording alone.
