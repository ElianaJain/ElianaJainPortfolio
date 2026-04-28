# UX Writing Case Study: Error states, form validation, and empty states for a field operations SaaS

**Product:** Fieldwork (fictional project management tool for field operations teams)
**Scope:** Three UI pattern types: empty states, form validation, error states
**Format:** Annotated Figma mockup with copy spec

---

## The problem

Most SaaS products treat error states, validation messages, and empty states as afterthoughts: copy that gets written at the end of a sprint, usually by an engineer, usually in the form of "Something went wrong. Please try again."

That copy fails users in the moments they most need clarity: when they've hit a wall, when they've made a mistake, or when they're new and don't yet know what the product does. For a field operations tool whose users are managing real-world work on a deadline, vague error copy isn't just frustrating. It's a productivity cost.

This sample demonstrates how intentional UX writing can turn those three pattern types into moments of trust rather than friction.

---

## Decisions and rationale

### Empty states: answer "why" before asking "what"

Empty states have two jobs. The first is obvious: tell the user the list is empty. The second is less obvious: give them a reason to care about filling it.

Most empty states skip the second job. "No projects yet. Create one!" tells the user nothing they didn't already know.

The Fieldwork empty states lead with benefit before CTA. "Projects help your team track field work, assign tasks, and keep everyone on the same page" answers the question a new user is actually asking (*why should I do this?*) before asking them to act. The CTA only appears after the value has been established.

The search empty state is different in one important way: it includes the user's actual query in the headline ("No results for 'bridge inspection Q3'"). This matters because it signals the system understood the input. Users who get a generic "no results" message often wonder if they searched correctly; users who see their query reflected back know the search ran and just didn't find anything. Small copy choice, meaningful difference in confidence.

I also wrote three distinct empty state variants rather than one, because the scenario matters:
- First use needs to motivate action
- Zero state (work done) needs to affirm rather than prompt
- No results needs to offer recovery paths

The same copy doesn't work for all three.

### Form validation: say what to do, not what went wrong

The standard validation message pattern is to name the error: "Invalid input," "Required field," "Incorrect format." These messages are accurate but not useful. They describe the problem from the system's perspective, not the user's.

Every validation message in this sample is written as an instruction, not a diagnosis:

- "Remove special characters. Only letters, numbers, and hyphens are allowed." Not "Invalid characters."
- "Start date can't be in the past. Choose today or a future date." Not "Invalid date."
- "A project lead is required before publishing." Not "Required field."

The third example includes a consequence ("before publishing") that the standard pattern omits entirely. Knowing *why* a field is required reduces frustration and speeds resolution. The user understands the system's logic rather than fighting an unexplained rule.

Two additional decisions worth noting:

The character count warning appears at 87% capacity, not at 100%. Users who hit a hard limit mid-sentence lose work. A warning at 85–90% gives them room to edit before they're stopped.

The error count ("Fix 3 errors to publish") appears near the submit button rather than at the top of the form. Users who scroll past validation errors and hit submit again shouldn't have to scroll back up to understand why it's still blocked.

### Error states: three sentences, three jobs

Every error state in this sample follows the same three-move structure: name the failure, provide reassurance or context, give a recovery path.

"Changes couldn't be saved. Your session expired while you were editing. Your draft is safe; sign back in to continue."

Move one names the failure without jargon. Move two answers the question the user is already panicking about ("did I lose my work?"). Move three gives a specific action.

This structure also informed what I left out. There's no apology in any of the error states. "We're sorry for the inconvenience" is a filler phrase that adds no information and slightly undermines the calm, professional tone the product needs. Field operations teams don't need sympathy. They need resolution.

The destructive confirmation modal applies a different set of decisions. The headline uses the object name rather than a generic "are you sure?" "Delete 'Northern Region Q3 Inspection'?" is specific enough that a user who clicked the wrong button will catch the mistake before confirming. The body includes a specific consequence count ("47 tasks") and names the side effect ("team members will lose access") because vague warnings don't stop confident users; specific consequences do.

The safe action is labeled "Keep project" rather than "Cancel." "Cancel" is ambiguous. It could mean canceling the deletion or canceling something else. "Keep project" is unambiguous and describes the outcome the user gets, not the action they're taking.

---

## Copy spec

The sample includes a copy spec tab documenting voice, tone by context, and six named rules with right/wrong examples. This was a deliberate choice.

A UX writing sample that only shows finished copy is incomplete. The spec shows the system behind the copy: the rules a team could apply consistently across the product without asking the UX writer to review every string. That's the difference between writing good copy and building a writing practice.

---

## What I'd push further

If this were a real product engagement rather than a sample, I'd want to test two things.

The first is the empty state body copy. Benefit-led language tests well in onboarding contexts, but field operations users are experienced professionals who may find it condescending. I'd A/B test a shorter, more direct variant ("No projects yet. Projects track tasks, timelines, and team assignments.") against the warmer version.

The second is the error count position. I placed it near the submit button based on the assumption that users scroll to the bottom before re-submitting. If analytics showed users re-submitting without scrolling, I'd move it to a sticky banner at the top of the form instead.

---

## Skills demonstrated

Content design for error recovery, empty states, and form validation. Voice and tone definition. Copy system documentation. Annotation for Figma handoff. Decision rationale for a non-UX audience.
