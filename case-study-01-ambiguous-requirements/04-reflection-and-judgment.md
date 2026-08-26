# Reflection: Where AI Helped, and Where It Didn't

## What AI was genuinely good at

- **Speed and completeness of the first-pass scan.** It caught every vague term across nine informal statements almost instantly. the kind of systematic line by line check that's easy to do carelessly under deadline pressure, precisely because it's tedious.
- **Surfacing implicit requirements.** The fail (open on fire) implication and the (role based access) implication were both correctly figured out from casual language, not only flagged where a keywords like "requirement" was present.
- **Producing a clean first structure to react to.** Even where I disagreed with its output, having a structured table to disagree with was faster than building that structure from a blank page myself.

## Where RE judgment had to override or add to the AI's output

- **Risk prioritization.** The AI presented all nine findings with equal visual weight. Recognizing that the fire fail-open item is a safety/legal compliance issue - categorically different in priority and verification path from wording like "user-friendly" - required domain judgment the AI didn't demonstrate on its own.
- **Knowing when *not* to let AI fill a gap.** For the user count and log retention items, the tempting move is to let the AI propose reasonable numbers. I deliberately didn't - inventing a number that sounds reasonable but isn't grounded in an actual stakeholder decision creates a false sense of completeness and introduces a real problem in a much more expensive stage (integration or audit). The correct RE move was to mark these as explicit open items, not to fabricate closure for requirements.
- **Scoping decisions.** The AI treated "visitors need to be handled somehow" as another line to analyze for missing information. The right call was to recognize it as **out of scope entirely** for this case and route it to a dedicated workshop: a judgment about process and stakeholder management, not requirement context.
- **Terminology and traceability discipline.** Formatting the final table with IDs, rationale, and defined verification methods per requirement and explicitly flagging every open item reflects standard RE quality practice (atomic, unambiguous, testable, traceable) that has to be applied with awareness; it isn't something the AI enforced unprompted.

## The takeaway

AI compressed the ambiguity detection step from roughly 20 minutes of manual (line by line) review to under a minute, and it didn't miss anything a careful manual pass would have caught. What it didn't do and what still needed a Requirements Engineer: was decide what actually mattered, what to leave open rather than safely resolve, and what deserved escalation before the next design workshop. That division of labor, not "AI replacing RE work," is what I think the next few years of this profession actually look like.
