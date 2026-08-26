# AI-Assisted Ambiguity Analysis

## The prompt
"You are assisting a Requirements Engineer in reviewing raw stakeholder
notes for a building access control system. For each statement below,
identify:

Any vague, subjective, or unquantified terms (e.g. "quickly",
"user-friendly", "reliable") that would need a measurable definition
before this could become a testable requirement.
Any implicit requirements: things clearly implied but not stated
outright.
Any missing information needed to make the statement complete
(actors, conditions, exceptions).

Do not rewrite the requirements yet, just flag the issues per
statement. This is for a first-pass ambiguity scan, not a final
requirements draft.

[raw stakeholder notes pasted here]
"

## AI output (first pass)

| # | Statement | Vague/unquantified terms | Implicit requirement | Missing information |
|---|---|---|---|---|
| 1 | "get into the building quickly" | "quickly" - no defined time threshold | - | What counts as the entry event: badge scan, door unlock, or physical entry? |
| 2 | "must be user-friendly so people don't need training" | "user-friendly", "no training" - both unmeasurable as stated | - | No acceptance criterion; "no training needed" is not independently verifiable |
| 3 | "only IT staff should get into the server room" | - | Role-based access control model implied | What happens for roles not explicitly mentioned? Is this allow-list or deny-list logic? |
| 4 | "handle a large number of users... growing a lot" | "large number", "a lot" - no figures | - | No target user count or growth timeline given |
| 5 | "security is a top priority... sensitive areas" | "top priority", "sensitive areas" - undefined | - | Which areas are "sensitive"? No enumerated list |
| 6 | "keep a log of who went where" | - | Audit logging requirement, likely with retention implications | Retention period not stated; log access/protection not stated |
| 7 | "lost badge... deal with that quickly" | "quickly" - no defined SLA | Badge revocation requirement implied | No defined process owner or channel for reporting a lost badge |
| 8 | "work reliably... can't have people locked out during a fire" | "reliably" - no measurable target | **Fail-safe/fail-open requirement during fire/emergency conditions** - this is a safety requirement, not just a reliability one | No reference to applicable fire-safety code or fail-open standard |
| 9 | "visitors need to be handled somehow" | "somehow" - explicitly acknowledged as undefined by the stakeholder | Temporary/escorted access requirement implied | No requirement scope defined at all yet - flagged as open |

## RE assessment of this output

The AI pass is genuinely useful here as it caught every vague term I'd expect, and it's fast: this table took seconds instead of the 15–20 minutes I'd normally spend manually marking up notes line by line.

But three things needed my judgment before this table was usable, not the AI's:

- **Row 8 is the most important finding in the whole table, and the AI underweighted it.** It listed it as one row among nine with the same visual weight as "user-friendly." In a real building system, "can't have people locked out during a fire" is a **life-safety fail-open requirement** - in most jurisdictions this is a *legal* requirement (doors must unlock automatically on fire alarm signal), not a nice-to-have requirement. An RE has to recognize that this single line item carries a completely different priority and verification path (compliance/code reference) than the others, and needs to be escalated and resolved before anything else on this list. The AI treated it as equivalent in importance to "user-friendly" - it isn't.
- **Row 3's "allow-list vs deny-list" framing is a good catch, but it's a design question, not a requirements question yet**, and needs to be directed back to IT Security as an open decision rather than assumed. I kept it as a flagged open question rather than letting the AI's phrasing quietly become an assumption in the next draft.
- **Row 9 didn't need more AI analysis: it needed a scoping decision.** The AI correctly noted the stakeholder input itself was undefined, but the right next step isn't to keep refining it with AI; it's to flag it explicitly as **out of scope for this requirement set / needs a followup workshop item**, so it isn't silently dropped or silently invented.

This is the pattern I want this whole repo to demonstrate: AI is very good at systematic and quick first-pass scanning. It's not yet reliable at knowing which of nine findings is a due diligence relevant safety issue versus a phrasing detail. that prioritization is still directly a RE judgment call.
