# Fieldwork UX Writing Sample — Figma Spec

> Build guide for recreating the Fieldwork dashboard UX writing sample in Figma.
> Use this alongside the HTML mockup. Every component, state, copy string, and spacing value is documented here.

---

## File structure

```
Fieldwork UX Writing Sample
├── Cover (thumbnail frame)
├── Page 1 — Empty states
├── Page 2 — Form validation
├── Page 3 — Error states
├── Page 4 — Copy spec
└── [FigJam link] — Annotation notes
```

Each page is a separate Figma frame at **1280 × 900px**. Content is centered in an **800px column** with **40px horizontal padding** on each side.

---

## Design tokens

Use these as Figma styles. Name them exactly as shown so they map to the copy spec.

### Colors

| Token name | Light mode | Usage |
|---|---|---|
| `color/text/primary` | #1A1A1A | Body, headings |
| `color/text/secondary` | #6B6B6B | Labels, hints, muted copy |
| `color/text/tertiary` | #9E9E9E | Placeholder, disabled |
| `color/bg/primary` | #FFFFFF | Card surface |
| `color/bg/secondary` | #F5F5F3 | Page background, annotation bg |
| `color/border/tertiary` | rgba(0,0,0,0.12) | Default borders |
| `color/border/secondary` | rgba(0,0,0,0.25) | Hover, emphasis borders |
| `color/status/error/text` | #A32D2D | Error message copy |
| `color/status/error/bg` | #FCEBEB | Error field background |
| `color/status/error/border` | #E24B4A | Error field border |
| `color/status/success/text` | #3B6D11 | Success message copy |
| `color/status/success/bg` | #EAF3DE | Success field background |
| `color/status/success/border` | #639922 | Success field border |
| `color/status/warning/text` | #854F0B | Warning copy |
| `color/status/warning/bg` | #FAEEDA | Warning banner background |
| `color/status/info/text` | #185FA5 | Info copy |
| `color/status/info/bg` | #E6F1FB | Info banner background |
| `color/status/danger/text` | #A32D2D | Danger/destructive copy |
| `color/status/danger/bg` | #FCEBEB | Danger banner background |

### Typography

| Token name | Size | Weight | Line height | Usage |
|---|---|---|---|---|
| `type/heading/lg` | 18px | 500 | 1.4 | Section headings |
| `type/heading/md` | 15px | 500 | 1.4 | Card headings, modal title |
| `type/body/md` | 13px | 400 | 1.6 | Body copy, form values |
| `type/body/sm` | 12px | 400 | 1.5 | Hints, secondary labels |
| `type/label/xs` | 11px | 500 | 1.4 | Uppercase labels, char count |
| `type/label/micro` | 10px | 500 | 1.4 | Annotation labels (all caps) |

Font family: **Inter** (fallback: system-ui). If Inter is unavailable, use **DM Sans**.

### Spacing

| Token | Value | Usage |
|---|---|---|
| `space/4` | 4px | Tight gaps, inline spacing |
| `space/8` | 8px | Component internal gaps |
| `space/12` | 12px | Between form elements |
| `space/16` | 16px | Card internal padding |
| `space/20` | 20px | Section padding |
| `space/24` | 24px | Between cards |
| `space/40` | 40px | Page horizontal margin |

### Corner radius

| Token | Value | Usage |
|---|---|---|
| `radius/sm` | 4px | Pills, badges, small chips |
| `radius/md` | 8px | Inputs, buttons, annotations |
| `radius/lg` | 12px | Cards, banners, modals |

---

## Component inventory

### 1. Top navigation bar

**Frame:** `Nav / Product bar`
**Size:** Full width × 44px
**Background:** `color/bg/primary`
**Border:** 0.5px bottom, `color/border/tertiary`
**Auto layout:** Horizontal, align center, padding 10px 16px, gap: auto (space between)

**Contents left:**
- Logo text: "Fieldwork" — `type/heading/md`, `color/text/primary`
- Separator: " / " — `type/body/md`, `color/text/secondary`
- Context: "Project dashboard" — `type/body/md`, `color/text/secondary`

**Contents right (Nav items):**
- Three items: "Projects", "Team" (active), "Reports"
- Inactive: `type/body/sm`, `color/text/secondary`, no background
- Active: `type/body/sm`, `color/text/primary`, weight 500, background `color/bg/secondary`, `radius/md`, padding 4px 10px

---

### 2. Tab bar

**Frame:** `Tabs / Horizontal`
**Size:** Full width × 36px
**Border:** 0.5px bottom, `color/border/tertiary`
**Auto layout:** Horizontal, align bottom, gap 0

**Tab item — inactive:**
- Label: `type/body/sm`, `color/text/secondary`
- Padding: 8px 16px
- Bottom border: 2px transparent

**Tab item — active:**
- Label: `type/body/sm`, `color/text/primary`, weight 500
- Bottom border: 2px `color/text/primary`

**Tab labels (in order):**
1. "Empty states"
2. "Form validation"
3. "Error states"
4. "Copy spec"

---

### 3. Card

**Frame:** `Card / Default`
**Background:** `color/bg/primary`
**Border:** 0.5px, `color/border/tertiary`
**Corner radius:** `radius/lg`
**Padding:** 20px
**Auto layout:** Vertical, gap 12px

---

### 4. Annotation component

**Frame:** `Annotation / Default`
**Background:** `color/bg/secondary`
**Border left:** 2px, `color/border/secondary`
**Corner radius:** 0 `radius/md` `radius/md` 0 (right corners only)
**Padding:** 10px 14px
**Auto layout:** Vertical, gap 4px

**Contents:**
- Label: `type/label/micro`, `color/text/secondary`, ALL CAPS — e.g. "VARIANT A — FIRST USE"
- Copy summary: `type/body/sm`, `color/text/primary`
- Note (optional): `type/body/sm`, `color/text/secondary`

**Layer naming convention:** `Annotation / [Pattern name] / [State]`
**Layer:** Place all annotations on a layer named `UX Copy Annotations`. Toggle visibility off for engineer handoff, on for design review.

---

### 5. Empty state

**Frame:** `Empty state / [Variant]`
**Alignment:** Center
**Padding:** 40px 24px
**Auto layout:** Vertical, align center, gap 0

**Icon container:**
- Size: 48 × 48px
- Shape: circle
- Background: `color/bg/secondary`
- Icon: 20 × 20px SVG, stroke `color/text/secondary`, stroke-width 1.2

**Spacing after icon:** 16px

**Title:**
- Style: `type/heading/md`
- Color: `color/text/primary`
- Margin bottom: 6px

**Body:**
- Style: `type/body/md`
- Color: `color/text/secondary`
- Max width: 320px
- Margin bottom: 20px

**Primary CTA button:**
- Style: `type/body/md`, weight 500
- Border: 0.5px `color/border/secondary`
- Radius: `radius/md`
- Padding: 7px 16px
- Background: `color/bg/primary`

**Secondary link (optional):**
- Style: `type/body/sm`
- Color: `color/text/secondary`
- Margin top: 8px
- Format: "Label text →"

**Variants:**

| Variant | Title | Body | CTA | Secondary link |
|---|---|---|---|---|
| First use | No projects yet | Projects help your team track field work, assign tasks, and keep everyone on the same page. | Create your first project | Learn how projects work → |
| Zero state | All caught up | No tasks are due today. Check upcoming tasks or review what your team completed this week. | View upcoming tasks | — |
| No results | No results for "[query]" | Try a shorter search, check your spelling, or remove filters. Projects older than 2 years are archived by default. | Clear search | Search archived projects → |

**Note on "No results" variant:** The query string in the title is a dynamic variable. In Figma, use a text variable named `{searchQuery}` and set a default value of "bridge inspection Q3" for the mockup.

---

### 6. Form input

**Frame:** `Input / [State]`
**States:** Default, Focus, Error, Success, Disabled

**Base styles:**
- Height: 36px
- Font: `type/body/md`
- Padding: 7px 10px
- Border: 0.5px `color/border/secondary`
- Radius: `radius/md`
- Background: `color/bg/primary`

**Error state:**
- Border: 0.5px `color/status/error/border`
- Background: `color/status/error/bg`

**Success state:**
- Border: 0.5px `color/status/success/border`
- Background: `color/bg/primary`

**Textarea:**
- Same as input but height: auto, min-height: 80px, resize: none

---

### 7. Field label

**Frame:** `Label / Default`
**Auto layout:** Horizontal, gap 2px, align baseline

**Label text:** `type/body/sm`, weight 500, `color/text/secondary`
**Required marker:** " *" — `type/body/sm`, `color/status/error/text`

---

### 8. Validation message

**Frame:** `Validation / [Type]`
**Auto layout:** Horizontal, gap 4px, align center
**Margin top:** 4px

**Error:**
- Icon: 12 × 12px circle with exclamation, stroke `color/status/error/text`
- Text: `type/label/xs`, `color/status/error/text`

**Success:**
- No icon
- Text: `type/label/xs`, `color/status/success/text`
- Copy: "Available"

**Hint:**
- No icon
- Text: `type/label/xs`, `color/text/secondary`

---

### 9. Character count

**Frame:** `Char count / [State]`
**Alignment:** Right
**Font:** `type/label/xs`
**Margin top:** 3px

| State | Color | Trigger |
|---|---|---|
| Default | `color/text/secondary` | 0–84% capacity |
| Warning | `color/status/warning/text` | 85–99% capacity |
| Over | `color/status/error/text` | 100%+ |

**Format:** "[current] / [max]" — e.g. "218 / 250"

---

### 10. Inline banner

**Frame:** `Banner / [Severity]`
**Auto layout:** Horizontal, gap 10px, align flex-start
**Padding:** 10px 14px
**Radius:** `radius/md`
**Margin bottom:** 16px

**Dot indicator:**
- Size: 6 × 6px circle
- Margin top: 3px (to align with first line of text)
- Color: matches severity text color

**Text:**
- `type/body/sm`
- Color: severity text token
- Bold lead: weight 500 for the first sentence or phrase

**Severities and copy:**

| Severity | Background | Text color | Dot color |
|---|---|---|---|
| Danger | `color/status/danger/bg` | `color/status/danger/text` | `color/status/danger/text` |
| Warning | `color/status/warning/bg` | `color/status/warning/text` | `color/status/warning/text` |
| Info | `color/status/info/bg` | `color/status/info/text` | `color/status/info/text` |
| Success | `color/status/success/bg` | `color/status/success/text` | `color/status/success/text` |

**Banner copy strings:**

| ID | Severity | Bold lead | Body |
|---|---|---|---|
| B1 | Danger | Changes couldn't be saved. | Your session expired while you were editing. Your draft is safe — sign back in to continue. |
| B2 | Danger | 3 team members couldn't be added. | The addresses below aren't in your organization. Check spelling or invite them as external collaborators. |
| B3 | Warning | This project has no active lead. | Tasks can still be assigned, but reports won't generate until a lead is set. |
| B4 | Info | File upload is temporarily unavailable. | Our team is working on it. You can add files directly to tasks once it's back — usually within an hour. |

---

### 11. Destructive confirmation modal

**Frame:** `Modal / Destructive`
**Size:** 360px wide
**Background:** `color/bg/secondary`
**Radius:** `radius/lg`
**Padding:** 24px
**Alignment:** Center
**Auto layout:** Vertical, gap 0

**Title:**
- Style: `type/heading/md`
- Margin bottom: 8px
- Format: Delete "[Object name]"?
- Default value: Delete "Northern Region Q3 Inspection"?

**Body:**
- Style: `type/body/md`
- Color: `color/text/secondary`
- Max width: 300px
- Margin bottom: 20px
- Copy: This will permanently delete the project and its 47 tasks. Team members will lose access. This can't be undone.

**Button row:**
- Auto layout: Horizontal, gap 8px, justify center

**Safe action button:**
- Label: "Keep project"
- Style: secondary button
- Border: 0.5px `color/border/secondary`

**Destructive action button:**
- Label: "Delete project"
- Background: `color/status/danger/bg`
- Border: 0.5px `color/status/danger/border`
- Text: `color/status/danger/text`

---

### 12. Form action bar

**Frame:** `Form / Action bar`
**Auto layout:** Horizontal, align center, gap 10px
**Padding top:** 16px
**Border top:** 0.5px `color/border/tertiary`

**Contents left:**
- Primary button: "Save as draft"
- Secondary button: "Cancel"

**Contents right (error state only):**
- Error count: `type/label/xs`, `color/text/secondary`
- Copy format: "Fix [N] errors to publish"
- Margin left: auto

---

## Page-by-page layout guide

### Page 1 — Empty states

**Layout:** Two-column grid (two cards side by side) + one full-width card below
**Column gap:** 16px
**Row gap:** 16px

**Left card:** Empty state / First use
**Right card:** Empty state / Zero state
**Full width card:** Empty state / No results

Each card has an annotation component below it inside the same parent frame.

---

### Page 2 — Form validation

**Layout:** Single column, full-width card

**Inside the card:**
- Info banner (B4 variant, noting static mockup context) — full width
- Form grid: two columns, gap 12px
  - Left: Project name input (error state)
  - Right: Project ID input (success state)
- Description textarea (warning char count) — full width
- Project lead input (error state, required) — full width
- Start date input (error state, past date) — full width
- Form action bar — full width

Each field group (label + input + message) is a vertically stacked auto-layout frame with gap 4px. Annotation components sit below each field group, outside the field frame.

---

### Page 3 — Error states

**Layout:** Single column, two cards stacked

**Card 1:** Page-level banner errors
- Section label: "Page-level banner errors"
- B1 banner + annotation
- Divider
- B2 banner + annotation
- Divider
- B3 banner + annotation
- Divider
- B4 banner + annotation

**Card 2:** Destructive action confirmation
- Section label: "Destructive action confirmation"
- Modal frame (centered, on secondary background)
- Annotation below modal

---

### Page 4 — Copy spec

**Layout:** Single column, two cards stacked

**Card 1:** Voice, tone, and rules
**Card 2:** Figma implementation notes

See the copy spec tab in the HTML mockup for exact copy strings.

---

## Handoff checklist

Before sharing the Figma file:

- [ ] All text styles applied using named tokens (no hardcoded hex values)
- [ ] All components named using the convention `ComponentType / Variant / State`
- [ ] `UX Copy Annotations` layer toggled off
- [ ] Each page has a frame named to match the tab label
- [ ] Cover frame includes: product name, sample type, author name, date
- [ ] All copy strings match this spec exactly — check against the HTML mockup
- [ ] Prototype connections set between tabs (tab click → navigate to page)
- [ ] File shared as "can view" for portfolio links, "can edit" for collaborators

---

## Copy inventory

All copy strings in the sample, consolidated for engineering handoff or translation.

### Empty states

| ID | Element | Copy |
|---|---|---|
| ES-01 | Title / First use | No projects yet |
| ES-02 | Body / First use | Projects help your team track field work, assign tasks, and keep everyone on the same page. |
| ES-03 | CTA / First use | Create your first project |
| ES-04 | Link / First use | Learn how projects work → |
| ES-05 | Title / Zero state | All caught up |
| ES-06 | Body / Zero state | No tasks are due today. Check upcoming tasks or review what your team completed this week. |
| ES-07 | CTA / Zero state | View upcoming tasks |
| ES-08 | Title / No results | No results for "{searchQuery}" |
| ES-09 | Body / No results | Try a shorter search, check your spelling, or remove filters. Projects older than 2 years are archived by default. |
| ES-10 | CTA / No results | Clear search |
| ES-11 | Link / No results | Search archived projects → |

### Form validation

| ID | Element | Copy |
|---|---|---|
| FV-01 | Error / Project name | Remove special characters. Only letters, numbers, and hyphens are allowed. |
| FV-02 | Success / Project ID | Available |
| FV-03 | Hint / Description | Describe the project scope. Used in reports and shared with external reviewers. |
| FV-04 | Error / Project lead | A project lead is required before publishing. |
| FV-05 | Error / Start date | Start date can't be in the past. Choose today or a future date. |
| FV-06 | Submit / Error count | Fix {errorCount} errors to publish |

### Error states

| ID | Element | Copy |
|---|---|---|
| ER-01 | Banner B1 | Changes couldn't be saved. Your session expired while you were editing. Your draft is safe — sign back in to continue. |
| ER-02 | Banner B2 | 3 team members couldn't be added. The addresses below aren't in your organization. Check spelling or invite them as external collaborators. |
| ER-03 | Banner B3 | This project has no active lead. Tasks can still be assigned, but reports won't generate until a lead is set. |
| ER-04 | Banner B4 | File upload is temporarily unavailable. Our team is working on it. You can add files directly to tasks once it's back — usually within an hour. |
| ER-05 | Modal title | Delete "{projectName}"? |
| ER-06 | Modal body | This will permanently delete the project and its {taskCount} tasks. Team members will lose access. This can't be undone. |
| ER-07 | Modal / Safe action | Keep project |
| ER-08 | Modal / Destructive action | Delete project |
