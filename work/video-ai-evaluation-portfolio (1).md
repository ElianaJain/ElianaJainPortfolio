# Evaluating AI-generated video: a rubric and side-by-side comparison log

**Author:** Elly Jain
**Status:** Template. Fill every [bracket] with your own work before publishing. Delete any section you did not complete.

---

## Why I built this

[2 to 3 sentences, your words. Say what you evaluated, why video, and how it builds on your image annotation and rubric work. Example direction: you spent years judging output quality against written standards, and you applied the same method to video.]

## Scope

- **Clips reviewed:** [number]
- **Sources:** [for example, public showcase galleries, official sample reels, open model samples. List them, and note that you did not generate the clips yourself.]
- **Models or tools compared:** [names]
- **Pairs judged side by side:** [number]
- **Time spent:** [hours]

## Rubric

Score each clip from 1 to 5 on every dimension. Write one sentence of evidence for any score of 2 or below.

| Dimension | What to check | 1 (fails) | 3 (mixed) | 5 (holds up) |
|---|---|---|---|---|
| Prompt adherence | Subject, action, setting, and style match the prompt | Misses the main subject or action | Gets the subject but drops details | Matches every stated element |
| Temporal consistency | Objects, faces, clothing, and background stay stable across frames | Visible flicker or identity changes | Minor drift that needs a second viewing | Stable from first to last frame |
| Motion and physics | Movement obeys weight, gravity, collisions, and fluids | Objects float, clip through each other, or move impossibly | Mostly plausible with one clear break | Plausible throughout |
| Anatomy and fine detail | Hands, fingers, teeth, text, and small objects | Morphing or extra or missing parts | Distortion in a few frames | Clean in every frame |
| Audio and lip sync | Speech aligns with mouth movement, and sound matches on-screen events | Clearly off or mismatched | Drifts over time | Aligned throughout |
| Visual quality | Resolution, compression artifacts, lighting, and color | Heavy artifacts or unstable lighting | Acceptable with noticeable flaws | Clean and coherent |

If a clip has no audio, mark audio and lip sync as N/A and do not count it in the total.

## Failure-mode taxonomy

Use these labels in the log so findings stay comparable across clips.

| Label | Definition |
|---|---|
| Flicker | Brightness, color, or texture changes between adjacent frames with no cause in the scene |
| Morphing | A shape changes form over time, such as fingers merging, faces shifting, or objects changing into others |
| Identity drift | A person or object looks like a different one by the end of the clip |
| Physics break | Motion contradicts weight, momentum, gravity, or contact |
| Object permanence error | An object appears, disappears, or duplicates without cause |
| Lip-sync drift | Mouth shapes fall out of step with the audio, often growing worse over time |
| Text corruption | Letters or signs change, blur, or become unreadable |
| Prompt miss | A stated element is absent or wrong |

## Pairwise method

1. Watch each clip at normal speed twice, then again at half speed or frame by frame for any suspected artifact.
2. Hide the model names until you finish. Randomize which clip you label A and which you label B.
3. Score both clips with the rubric.
4. Pick a winner. If the totals tie, pick the clip with fewer severe failures. If you still cannot separate them, record a tie.
5. Write the reason for your pick in two sentences or fewer, with timestamps.
6. Optional: update an Elo rating for each model after each pair. Start every model at 1000 and use a K-factor of 32. State in the write-up that the sample is too small to rank models.

### Writing good evaluation notes

Incorrect: "Clip B looks worse and kind of weird."

Correct: "Clip B shows morphing in the left hand at 0:03 to 0:05, where the fingers merge into the cup. Clip A holds the hand shape throughout."

## Comparison log

Copy this block once per pair.

### Pair [number]: [short prompt summary]

- **Prompt:** [exact prompt, if the source published it]
- **Clip A source and length:** [link, seconds]
- **Clip B source and length:** [link, seconds]

| Dimension | Clip A | Clip B |
|---|---|---|
| Prompt adherence | [1-5] | [1-5] |
| Temporal consistency | [1-5] | [1-5] |
| Motion and physics | [1-5] | [1-5] |
| Anatomy and fine detail | [1-5] | [1-5] |
| Audio and lip sync | [1-5 or N/A] | [1-5 or N/A] |
| Visual quality | [1-5] | [1-5] |
| **Total** | [sum] | [sum] |

**Failure-mode log**

| Clip | Timestamp | Label | Severity (minor, major, severe) | Note |
|---|---|---|---|---|
| [A or B] | [0:00 to 0:00] | [label] | [level] | [what you saw] |

**Winner:** [A, B, or tie]
**Reason:** [two sentences or fewer, with timestamps]

---

## Summary of findings

| Model or tool | Pairs won | Pairs lost | Ties | Most common failure |
|---|---|---|---|---|
| [name] | [n] | [n] | [n] | [label] |

**Patterns I saw:** [3 to 5 sentences. Report only what your log shows.]

## Limits of this work

- The sample is small and the clips are not randomly selected.
- I judged public clips and did not control the prompts.
- My scores come from one reviewer. [If you re-scored a subset later, report how often your scores matched.]
- I did not measure inter-rater agreement with other reviewers.

## What I would do next

[2 to 3 sentences. For example, add a second reviewer to measure agreement, expand the lip-sync set, or test the rubric on longer clips.]

## Connection to my earlier work

- **Image annotation at Meta:** [one sentence on how the standards and consistency work carries over]
- **Joule quality testing at SAP Ariba:** [one sentence on rubrics and human-in-the-loop review]
- **UX writing practice app:** [one sentence on rubric-based scoring]

---

## Completion checklist

- [ ] At least 10 pairs judged and logged
- [ ] Every score of 2 or below has a one-sentence evidence note
- [ ] Every failure has a timestamp and a taxonomy label
- [ ] Source links work, and you credit each clip's origin
- [ ] You claim only what the log supports
- [ ] The finished piece is published on Substack or Hashnode, and the link is on your resume
