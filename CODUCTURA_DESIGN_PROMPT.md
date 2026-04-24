# CODUCTURA — Complete UI/UX Design System Prompt

> This is the full design specification for CODUCTURA. Implement every screen, component, color, 
> typeface, animation, and copy string exactly as defined below. Do not deviate from this system.
> Every decision here is intentional. The goal: serious, smart, trustable, familiar, 
> psychologically comforting, strong, and easy to use.

---

## DESIGN PHILOSOPHY

CODUCTURA is a tool for people who carry real operational weight — directors, managers, 
team leads. It should feel like a trusted senior colleague: calm, precise, never alarmist, 
always clear. The interface earns trust by being consistent, uncluttered, and deeply readable.

Design principles in priority order:
1. **Clarity above all** — the user always knows where they are and what to do next
2. **Calm authority** — serious without being cold, strong without being aggressive
3. **Data density with breathing room** — pack information in, but give it space to be read
4. **Familiar patterns, exceptional execution** — use known patterns (table, sidebar, cards) but 
   execute them with precision and intention
5. **Nothing decorative that isn't functional** — every visual element earns its place

Aesthetic reference: Bloomberg Terminal discipline, Notion warmth, Linear precision, 
Stripe trustworthiness. Not startup-playful. Not cold enterprise blue. Something richer.

---

## COLOR SYSTEM

Define all colors as CSS custom properties on :root. Use these tokens everywhere — never 
hardcode hex values in components.

```css
:root {
  /* ── Brand Core ─────────────────────────────────────────────────────── */
  --brand-navy:        #0D1B2A;   /* Primary brand color. Deep, authoritative navy. */
  --brand-navy-mid:    #1A2E45;   /* Slightly lighter navy for surfaces */
  --brand-navy-light:  #243B55;   /* Hover/active states on dark surfaces */
  --brand-teal:        #0EA5C9;   /* Primary accent. Precision and intelligence. */
  --brand-teal-light:  #38BDF8;   /* Hover states, highlights */
  --brand-teal-subtle: #E0F7FD;   /* Light tinted backgrounds */
  --brand-amber:       #F59E0B;   /* Escalations, warnings, human urgency */
  --brand-amber-light: #FEF3C7;   /* Amber backgrounds */

  /* ── Semantic Colors ─────────────────────────────────────────────────── */
  --color-success:     #10B981;   /* Completed, resolved, positive states */
  --color-success-bg:  #ECFDF5;
  --color-warning:     #F59E0B;   /* Overdue, pending, caution */
  --color-warning-bg:  #FFFBEB;
  --color-danger:      #EF4444;   /* Blocked, critical, errors */
  --color-danger-bg:   #FEF2F2;
  --color-info:        #0EA5C9;   /* Informational states */
  --color-info-bg:     #E0F7FD;
  --color-escalation:  #7C3AED;   /* Escalated status — distinct purple */
  --color-escalation-bg: #F5F3FF;

  /* ── Neutral Scale (Light Mode — App Default) ────────────────────────── */
  --gray-50:  #F8FAFC;
  --gray-100: #F1F5F9;
  --gray-200: #E2E8F0;
  --gray-300: #CBD5E1;
  --gray-400: #94A3B8;
  --gray-500: #64748B;
  --gray-600: #475569;
  --gray-700: #334155;
  --gray-800: #1E293B;
  --gray-900: #0F172A;

  /* ── Surfaces ────────────────────────────────────────────────────────── */
  --surface-base:      #FFFFFF;     /* Main content background */
  --surface-raised:    #F8FAFC;     /* Cards, table rows, slight elevation */
  --surface-overlay:   #F1F5F9;     /* Sidebar, secondary panels */
  --surface-sunken:    #E2E8F0;     /* Input backgrounds, inset areas */
  --surface-inverse:   #0D1B2A;     /* Dark surfaces (sidebar, header) */

  /* ── Text ─────────────────────────────────────────────────────────────── */
  --text-primary:      #0F172A;     /* Main body text */
  --text-secondary:    #475569;     /* Labels, supporting text */
  --text-muted:        #94A3B8;     /* Placeholders, disabled, hints */
  --text-inverse:      #F8FAFC;     /* Text on dark surfaces */
  --text-inverse-muted:#94A3B8;     /* Muted text on dark surfaces */
  --text-accent:       #0EA5C9;     /* Links, active items */

  /* ── Borders ─────────────────────────────────────────────────────────── */
  --border-subtle:     #E2E8F0;     /* Most borders — light, barely there */
  --border-default:    #CBD5E1;     /* Standard borders */
  --border-strong:     #94A3B8;     /* Focused inputs, emphasis */
  --border-inverse:    #243B55;     /* Borders on dark surfaces */

  /* ── Shadows ─────────────────────────────────────────────────────────── */
  --shadow-xs:  0 1px 2px rgba(15, 23, 42, 0.04);
  --shadow-sm:  0 1px 3px rgba(15, 23, 42, 0.08), 0 1px 2px rgba(15, 23, 42, 0.04);
  --shadow-md:  0 4px 6px rgba(15, 23, 42, 0.06), 0 2px 4px rgba(15, 23, 42, 0.04);
  --shadow-lg:  0 10px 15px rgba(15, 23, 42, 0.08), 0 4px 6px rgba(15, 23, 42, 0.04);
  --shadow-xl:  0 20px 25px rgba(15, 23, 42, 0.10), 0 8px 10px rgba(15, 23, 42, 0.04);
  --shadow-teal: 0 0 0 3px rgba(14, 165, 201, 0.15);  /* Focus ring */

  /* ── Radius ──────────────────────────────────────────────────────────── */
  --radius-xs:  3px;
  --radius-sm:  6px;
  --radius-md:  8px;
  --radius-lg:  12px;
  --radius-xl:  16px;
  --radius-full: 9999px;

  /* ── Spacing Scale ────────────────────────────────────────────────────── */
  --space-1:  4px;
  --space-2:  8px;
  --space-3:  12px;
  --space-4:  16px;
  --space-5:  20px;
  --space-6:  24px;
  --space-8:  32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;
  --space-20: 80px;
  --space-24: 96px;

  /* ── Transitions ──────────────────────────────────────────────────────── */
  --transition-fast:   100ms ease;
  --transition-base:   180ms ease;
  --transition-slow:   300ms ease;
  --transition-spring: 400ms cubic-bezier(0.175, 0.885, 0.32, 1.275);
}
```

---

## TYPOGRAPHY

### Font Families

```css
/* Import in <head> */
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;1,9..40,400&family=JetBrains+Mono:wght@400;500&display=swap');

:root {
  --font-display: 'Syne', sans-serif;       /* Headings, logo, hero text */
  --font-body:    'DM Sans', sans-serif;    /* All body text, UI labels, buttons */
  --font-mono:    'JetBrains Mono', monospace; /* Task IDs, timestamps, code */
}
```

**Why these fonts:**
- **Syne** — geometric, authoritative, slightly unconventional. Conveys intelligence and 
  precision without being cold. Has real personality in display sizes.
- **DM Sans** — warm, readable, slightly humanist. Feels familiar and approachable. 
  Excellent at small sizes in dense UIs. Never tiring to read.
- **JetBrains Mono** — the best monospace for data. Clear character distinction, 
  great at small sizes, never looks like an afterthought.

### Type Scale

```css
/* Display — Landing page hero, section titles */
.text-display-xl  { font: 800 72px/1.05 var(--font-display); letter-spacing: -2px; }
.text-display-lg  { font: 700 56px/1.1  var(--font-display); letter-spacing: -1.5px; }
.text-display-md  { font: 700 40px/1.15 var(--font-display); letter-spacing: -1px; }
.text-display-sm  { font: 600 32px/1.2  var(--font-display); letter-spacing: -0.5px; }

/* Headings — App section titles, card headers */
.text-h1 { font: 600 28px/1.3 var(--font-display); letter-spacing: -0.3px; }
.text-h2 { font: 600 22px/1.35 var(--font-display); letter-spacing: -0.2px; }
.text-h3 { font: 600 18px/1.4 var(--font-body); letter-spacing: -0.1px; }
.text-h4 { font: 600 15px/1.4 var(--font-body); }
.text-h5 { font: 500 13px/1.4 var(--font-body); text-transform: uppercase; letter-spacing: 0.6px; }

/* Body — Content, descriptions */
.text-body-lg  { font: 400 17px/1.6 var(--font-body); }
.text-body-md  { font: 400 15px/1.6 var(--font-body); }
.text-body-sm  { font: 400 13px/1.5 var(--font-body); }
.text-body-xs  { font: 400 11px/1.5 var(--font-body); }

/* UI Labels — Navigation, buttons, table headers */
.text-label-lg { font: 500 15px/1.4 var(--font-body); }
.text-label-md { font: 500 13px/1.4 var(--font-body); }
.text-label-sm { font: 500 11px/1.4 var(--font-body); letter-spacing: 0.3px; }

/* Mono — Task IDs, numbers, timestamps */
.text-mono-md  { font: 500 13px/1.4 var(--font-mono); }
.text-mono-sm  { font: 400 12px/1.4 var(--font-mono); }
```

---

## ICONOGRAPHY

Use **Lucide React** icons throughout. Never mix icon libraries.
Default icon size: 16px in tables and labels, 20px in navigation, 24px in headings.
Stroke width: 1.5px always (not 2px — it reads as lighter and more refined).

Key icons per context:
- Dashboard → `LayoutDashboard`
- Projects → `FolderOpen`
- Tasks → `CheckSquare`
- Decisions & Blockers → `AlertCircle`
- Settings → `Settings2`
- Analytics → `BarChart3`
- Escalation → `ArrowUpCircle`
- Blocker → `ShieldAlert`
- Decision → `HelpCircle`
- Files → `Paperclip`
- User → `UserCircle2`
- Team → `Users2`
- Department → `Building2`
- Calendar → `CalendarDays`
- Export → `Download`
- Filter → `SlidersHorizontal`
- Add → `Plus`
- Search → `Search`
- Overdue → `Clock3`
- Completed → `CheckCircle2`
- In Progress → `Circle` (half-filled with CSS)
- Long Running → `Timer`
- Notification → `Bell`
- Audit → `ScrollText`
- Guide/Note → `Lightbulb`

---

## COMPONENT LIBRARY

### Buttons

```
PRIMARY BUTTON
Background: var(--brand-navy)
Text: var(--text-inverse)
Border: none
Border-radius: var(--radius-sm)
Padding: 10px 20px
Font: var(--font-body) 500 14px
Hover: background var(--brand-navy-light), box-shadow var(--shadow-sm)
Active: background #0a1520, transform: translateY(1px)
Transition: var(--transition-base)

ACCENT BUTTON (Primary CTA on landing)
Background: var(--brand-teal)
Text: white
Hover: background var(--brand-teal-light)
Box-shadow on hover: 0 4px 12px rgba(14, 165, 201, 0.3)

SECONDARY BUTTON
Background: transparent
Text: var(--text-primary)
Border: 1.5px solid var(--border-default)
Hover: background var(--gray-50), border-color var(--border-strong)

GHOST BUTTON
Background: transparent
Text: var(--text-secondary)
Hover: background var(--gray-100), text var(--text-primary)

DANGER BUTTON
Background: var(--color-danger)
Text: white
Hover: background #dc2626

BUTTON SIZES:
sm: padding 6px 12px, font 13px, radius var(--radius-xs)
md: padding 10px 20px, font 14px, radius var(--radius-sm) [default]
lg: padding 13px 28px, font 15px, radius var(--radius-sm)

ICON BUTTON (square, no text):
Size: 32px × 32px (sm), 36px × 36px (md)
Background: transparent
Hover: background var(--gray-100)
Border-radius: var(--radius-sm)
```

### Inputs & Form Fields

```
TEXT INPUT
Height: 38px
Border: 1.5px solid var(--border-default)
Border-radius: var(--radius-sm)
Background: white
Padding: 0 12px
Font: var(--font-body) 14px var(--text-primary)
Placeholder: var(--text-muted)

Focus state:
  border-color: var(--brand-teal)
  outline: none
  box-shadow: var(--shadow-teal)

Error state:
  border-color: var(--color-danger)
  box-shadow: 0 0 0 3px rgba(239, 68, 68, 0.12)

Disabled:
  background: var(--gray-50)
  text: var(--text-muted)
  cursor: not-allowed

TEXTAREA: Same as input but min-height: 80px, padding: 10px 12px, resize: vertical

SELECT/DROPDOWN:
Same visual as input
Chevron icon (12px) right-aligned using var(--text-muted)

LABEL:
font: var(--font-body) 500 13px
color: var(--text-secondary)
margin-bottom: 6px
display: block

Required indicator: red asterisk (*) in var(--color-danger)

SEARCH INPUT:
Search icon (16px) left-padded: padding-left: 36px
Clear button when value present: × icon right-aligned

DATE PICKER:
Same as input
Calendar icon right-aligned
Opens Shadcn Calendar component below the input
Calendar header: var(--font-display) for month/year
Selected day: background var(--brand-navy), text white, border-radius var(--radius-full)
Today indicator: underline or dot in var(--brand-teal)
```

### Checkboxes & Radio

```
CHECKBOX:
Size: 16px × 16px
Border: 1.5px solid var(--border-default)
Border-radius: var(--radius-xs)
Checked: background var(--brand-navy), border var(--brand-navy), checkmark in white (stroke 2.5px)
Hover: border-color var(--brand-teal)
Focus: box-shadow var(--shadow-teal)
Indeterminate: background var(--brand-navy) with horizontal line

ROW CHECKBOX in task table:
Appears on row hover and when any row is selected
16px, same as above
```

### Badge / Status Pills

```
Base: inline-flex, align-center, padding 2px 10px, border-radius var(--radius-full)
Font: var(--font-body) 500 12px
Border: 1px solid (slightly darker than bg)

Status variants:
  NOT STARTED:  bg #F1F5F9,   text #475569,   border #CBD5E1  → "Not Started"
  IN PROGRESS:  bg #DBEAFE,   text #1D4ED8,   border #BFDBFE  → "In Progress"
  BLOCKED:      bg #FEE2E2,   text #DC2626,   border #FECACA  → "Blocked"
  COMPLETED:    bg #DCFCE7,   text #16A34A,   border #BBF7D0  → "Completed"
  CANCELLED:    bg #F1F5F9,   text #94A3B8,   border #E2E8F0, text-decoration: line-through
  ESCALATED:    bg #F5F3FF,   text #6D28D9,   border #DDD6FE  → "Escalated"
  REOPENED:     bg #FEF3C7,   text #D97706,   border #FDE68A  → "Reopened"

Decision variants:
  PENDING:      bg #FEF3C7,   text #B45309,   border #FDE68A  → "Decision Pending"
  RESOLVED:     bg #DCFCE7,   text #15803D,   border #BBF7D0  → "Resolved"

Blocker variants:
  OPEN:         bg #FEE2E2,   text #DC2626,   border #FECACA  → "Blocker Open"
  RESOLVED:     bg #DCFCE7,   text #15803D,   border #BBF7D0  → "Resolved"
  NONE:         — (no badge shown)

Task Type:
  MINI:         bg #F8FAFC,   text #64748B   → "Mini ≤30m"
  SMALL:        bg #EFF6FF,   text #3B82F6   → "Small"
  MEDIUM:       bg #FFF7ED,   text #EA580C   → "Medium"
  DAY:          bg #F0FDF4,   text #16A34A   → "Day"
  LONG RUNNING: bg #FDF4FF,   text #9333EA   → "Long Running"

Add a 6px colored dot before text for all status badges.
Dot color matches the text color.
```

### Cards

```
BASE CARD:
Background: white
Border: 1px solid var(--border-subtle)
Border-radius: var(--radius-lg)
Box-shadow: var(--shadow-xs)
Padding: 20px 24px

Hover (when clickable):
  border-color: var(--border-default)
  box-shadow: var(--shadow-md)
  transform: translateY(-1px)
  transition: var(--transition-base)

METRIC CARD (Analytics bar):
Width: 180px min (scrollable row)
Height: 88px
Padding: 16px 18px
Background: white
Border: 1px solid var(--border-subtle)
Border-radius: var(--radius-md)
Left border accent: 3px solid [metric-color] (left side)

  Metric label: font-body 500 12px, text-muted, uppercase, letter-spacing 0.5px
  Metric value: font-display 700 28px, text-primary
  Trend indicator: +/- arrow with % in font-body 12px
  
  Metric colors by type:
    Open Tasks:      var(--brand-teal)
    Overdue:         var(--color-danger)
    Long Running:    var(--color-escalation)
    Decisions:       var(--color-warning)
    Blockers:        var(--color-danger)
    Completed:       var(--color-success)
    Escalations:     var(--color-escalation)
    Delay Index:     var(--brand-amber)

PROJECT CARD:
Width: 280px (in grid, 3-4 per row)
Padding: 20px
Border-radius: var(--radius-lg)
Top border: 3px solid var(--brand-teal)
  
  Header row: Project name (h4) + status badge
  Analytics grid: 2×3 grid of mini metrics (label + value)
  Mini metrics: font-mono 600 18px for numbers, font-body 11px for labels
  Footer: "View Project →" link in var(--brand-teal)
  Click: whole card is clickable
```

### Dropdown Menus & Popovers

```
DROPDOWN PANEL:
Background: white
Border: 1px solid var(--border-subtle)
Border-radius: var(--radius-md)
Box-shadow: var(--shadow-xl)
Padding: 6px
Min-width: 180px
Animation: fade in + translateY(-4px) → translateY(0) over 150ms

DROPDOWN ITEM:
Padding: 8px 12px
Border-radius: var(--radius-sm)
Font: font-body 14px text-primary
Icon: 16px, text-muted, margin-right: 10px
Hover: background var(--gray-50), text var(--text-primary)
Active: background var(--brand-teal-subtle), text var(--brand-teal)
Destructive: text var(--color-danger), hover bg var(--color-danger-bg)

SEPARATOR: 1px solid var(--border-subtle), margin 4px 0

SEARCHABLE DROPDOWN:
Search input at top of panel (full width, no border, border-bottom only)
Results list below, max-height 240px, overflow-y: auto
No results state: "No matches" in text-muted, centered
```

### Table (Task Table)

```
TABLE WRAPPER:
Background: white
Border: 1px solid var(--border-subtle)
Border-radius: var(--radius-lg)
Box-shadow: var(--shadow-xs)
Overflow: hidden

TABLE HEADER:
Background: var(--gray-50)
Border-bottom: 1.5px solid var(--border-subtle)
Height: 40px
Position: sticky, top: 0, z-index: 10

  Column header cell:
  Padding: 0 12px
  Font: font-body 500 12px, text-muted, uppercase, letter-spacing 0.5px
  Cursor: pointer (if sortable)
  Sort icon: Lucide ArrowUpDown 12px, appears on hover
  Active sort: brand-teal tint on header cell, arrow icon solid
  Resize handle: 3px wide, right edge of header, cursor: col-resize

TABLE ROW:
Height: 40px (standard), 48px (with secondary content)
Border-bottom: 1px solid var(--border-subtle)
Transition: background var(--transition-fast)

  Default:   background white
  Hover:     background var(--gray-50)
  Selected:  background #EFF6FF (very subtle blue tint), left border 2px solid brand-teal
  Focused:   outline: none (use row highlight instead)
  Overdue:   left border 2px solid var(--color-danger)
  Escalated: left border 2px solid var(--color-escalation)
  Blocked:   left border 2px solid var(--color-danger)

TABLE CELL:
Padding: 0 12px
Font: font-body 14px text-primary
Vertical-align: middle
White-space: nowrap (unless description/note column)

DESCRIPTION COLUMN: max-width 320px, truncate with ellipsis, full text on hover tooltip
NOTE COLUMN: text-muted, italic, font 13px
TASK ID COLUMN: font-mono 500 13px, text-muted, width: 90px
% COMPLETION: Progress bar 80px wide, 6px tall, rounded, 
              background var(--gray-200), fill var(--brand-teal)
              Show number (13px, font-mono, text-secondary) right of bar
FILES COLUMN: Paperclip icon (14px) + count badge if files attached
              text-muted when empty, text-primary when has files

INLINE EDIT:
Click cell → transform to input/dropdown
Input style: no border, no padding, full cell width
Outline: none (cell itself shows focus ring)
Save: Enter or click away (blur)
Cancel: Escape

ADD ROW:
Last row of table OR floating "+ Add Task" button
Row with dashed border, text-muted "+ Add Task" centered
Hover: background var(--gray-50), text text-primary

EMPTY STATE:
Center in table area, height 240px
Icon: CheckSquare 32px, text-muted
Title: "No tasks yet" font-body 500 15px text-secondary
Subtitle: "Click + Add Task to create your first task" font-body 13px text-muted
CTA button: "+ Add Task" accent button
```

### Sidebar Navigation

```
SIDEBAR:
Width: 240px (expanded), 56px (collapsed)
Background: var(--brand-navy)
Border-right: 1px solid var(--border-inverse)
Height: 100vh, position: fixed, left: 0, top: 0
Display: flex, flex-direction: column
Transition: width 250ms ease

SIDEBAR TOP:
Padding: 20px 16px
Logo + wordmark (see Logo section)
Collapse toggle button: top-right of sidebar, icon-only

NAVIGATION SECTION:
Padding: 8px
Label above group: font-body 500 11px, text-inverse-muted, uppercase, 
                   letter-spacing: 0.7px, padding: 16px 12px 6px 12px

NAV ITEM:
Height: 38px
Padding: 0 12px
Border-radius: var(--radius-sm)
Display: flex, align-items: center, gap: 10px
Font: font-body 500 14px text-inverse-muted
Icon: 18px, color: text-inverse-muted
Cursor: pointer
Transition: all var(--transition-fast)

Hover:
  Background: var(--brand-navy-light)
  Text + icon: text-inverse

Active:
  Background: rgba(14, 165, 201, 0.15)
  Text: white
  Icon: var(--brand-teal)
  Left border: 2px solid var(--brand-teal)
  Border-radius: 0 var(--radius-sm) var(--radius-sm) 0

BADGE on nav item (for counts):
Right side of nav item
Background: var(--brand-teal)
Text: white, font-mono 500 11px
Padding: 1px 6px, border-radius: var(--radius-full)
(Danger color for escalations/overdue counts)

GUIDANCE NOTE BANNER (Supreme Admin):
Bottom of sidebar above bottom section
Background: rgba(245, 158, 11, 0.12)
Border: 1px solid rgba(245, 158, 11, 0.3)
Border-radius: var(--radius-md)
Padding: 10px 12px
Margin: 8px
Icon: Lightbulb 14px, color: brand-amber
Text: font-body 400 12px, color: FEF3C7 (light amber-white)
Label: "Guidance" font-body 500 11px uppercase text-amber above text

SIDEBAR BOTTOM:
Padding: 16px
Border-top: 1px solid var(--border-inverse)
User avatar + name + role
Settings link
Logout button
```

### Top Header Bar (App)

```
HEIGHT: 56px
Background: white
Border-bottom: 1px solid var(--border-subtle)
Position: sticky, top: 0, z-index: 20
Padding: 0 24px
Display: flex, justify-content: space-between, align-items: center

LEFT: Breadcrumb navigation
  Project → Folder → (Table) separated by chevron icon (12px, text-muted)
  Current page: font-body 600 15px text-primary
  Parent pages: font-body 400 15px text-muted, clickable, hover: text-primary

RIGHT ACTIONS (left to right):
  1. Global search: Ghost button with Search icon + "Search..." placeholder
     Opens command palette (see below)
  2. Notifications bell: icon button, badge when unread
  3. Avatar: 32px circle, initials or photo
     Dropdown: Profile, Settings, Sign out
```

### Command Palette (Global Search)

```
Trigger: Ctrl+K / Cmd+K or clicking search button
OVERLAY: fixed, full screen, background rgba(15,23,42,0.5), backdrop-blur: 4px
Animation: fade in 150ms

PALETTE PANEL:
Width: 560px
Max-height: 480px
Background: white
Border-radius: var(--radius-xl)
Box-shadow: var(--shadow-xl)
Position: centered, top: 18% of viewport

SEARCH INPUT:
Height: 52px
Border: none
Border-bottom: 1px solid var(--border-subtle)
Font: font-body 500 16px text-primary
Padding: 0 20px 0 48px
Search icon: 18px, left-aligned at 16px

RESULTS:
Grouped sections: Projects, Tasks, People, Settings
Section label: font-body 500 11px text-muted uppercase, padding 8px 16px
Result item: height 44px, padding 0 16px, flex, gap 12px
  Icon: 16px, text-muted
  Primary text: font-body 14px text-primary
  Secondary text: font-body 12px text-muted (project name, status, etc.)
  Keyboard hint: right side, kbd-styled badge showing Enter
  Hover/selected: background var(--gray-50)

EMPTY: Icon + "No results for..." in text-muted
FOOTER: "Press ↑↓ to navigate, Enter to select, Esc to dismiss"
  Font: font-body 12px text-muted, padding 12px 16px, border-top
```

### Modals & Dialogs

```
OVERLAY: fixed, full screen, background rgba(15,23,42,0.45), backdrop-blur: 2px
Animation: fade-in 150ms

MODAL PANEL:
Background: white
Border-radius: var(--radius-xl)
Box-shadow: var(--shadow-xl)
Animation: scale from 0.95 + fade in 200ms (spring easing)

SIZES:
  sm: width 400px
  md: width 560px (default)
  lg: width 720px
  xl: width 920px (for task detail, analytics)
  Full-screen: for file picker when on mobile

MODAL HEADER:
Padding: 20px 24px
Border-bottom: 1px solid var(--border-subtle)
Title: font-display 600 18px text-primary
Subtitle: font-body 14px text-secondary (optional, below title)
Close button: top-right, 32px icon button, X icon

MODAL BODY:
Padding: 24px
Overflow-y: auto
Max-height: 70vh

MODAL FOOTER:
Padding: 16px 24px
Border-top: 1px solid var(--border-subtle)
Button group: right-aligned, gap 10px
Cancel: secondary button
Confirm/Save: primary or accent button (depends on action)
Destructive confirm: danger button
```

### Notifications Panel

```
Trigger: Bell icon in header
PANEL: 
  Width: 380px
  Position: fixed top-right, below header
  Background: white
  Border: 1px solid var(--border-subtle)
  Border-radius: var(--radius-lg)
  Box-shadow: var(--shadow-xl)
  Max-height: 520px
  Animation: slide down + fade in 180ms

HEADER:
  Title: "Notifications" font-display 600 16px
  "Mark all read" link: font-body 500 13px text-accent
  Border-bottom

NOTIFICATION ITEM:
  Padding: 14px 16px
  Border-bottom: 1px solid var(--border-subtle)
  Unread: background var(--gray-50), left border 3px solid brand-teal
  Icon: 18px, colored per type, flex-shrink: 0
  Title: font-body 500 14px text-primary (unread) / text-secondary (read)
  Body: font-body 13px text-muted
  Time: font-body 12px text-muted, right-aligned
  Hover: background var(--gray-50)

EMPTY: Centered, Bell icon 24px text-muted, "You're all caught up"
```

### Tooltip

```
Background: var(--gray-900)
Text: white, font-body 12px
Padding: 6px 10px
Border-radius: var(--radius-sm)
Box-shadow: var(--shadow-md)
Max-width: 220px
Animation: fade in 100ms, delay 400ms on hover
Arrow: 5px triangle pointing toward trigger
```

### Analytics Bar (Dashboard)

```
CONTAINER:
Horizontal scroll (hide scrollbar but allow scroll)
Display: flex, gap: 12px, padding: 20px 24px
Background: white
Border-bottom: 1px solid var(--border-subtle)
Scroll shadows: gradient mask on left/right edges when content overflowed

SECTION LABELS:
Appear above group of related cards
Font: font-body 500 11px text-muted uppercase letter-spacing 0.6px
"Personal" / "Projects" / "Team" / "Organisation"

METRIC CARD: see Card spec above

LOADING STATE: Skeleton shimmer using gradient animation,
  same card dimensions, no content, shimmer: 
  background: linear-gradient(90deg, gray-100 25%, gray-50 50%, gray-100 75%)
  background-size: 200% 100%
  animation: shimmer 1.4s infinite
```

### Escalation Grouper

```
SELECTION MODE:
When rows are selected, toolbar appears above table:
  Fixed bar: background white, border-top 1.5px solid brand-teal
  Height: 48px, padding 0 16px
  Left: "{N} tasks selected" font-body 500 14px text-primary
  Right: "Group & Escalate" amber button, "Clear selection" ghost button

GROUP BUILDER MODAL (lg size):
  Left panel: Task list (selected tasks with checkboxes, title, status badge)
  Right panel: Group hierarchy builder
    - Title input for root group
    - Sub-group adder (+ Add Sub-group)
    - Drag-to-nest via handle icon
    - Preview of nested structure in tree view
  
  Below tree: "Escalate individually" vs "Escalate as group" toggle (pill switch)
  Escalation reason: textarea (required)
  Target role: auto-shown (computed from hierarchy), read-only, info style
  Footer: "Escalate" amber button, "Cancel"
```

---

## LAYOUT SYSTEM

### App Shell

```
Full viewport layout:

┌──────────────────────────────────────────────────────┐
│ SIDEBAR (240px, navy)  │  MAIN CONTENT AREA          │
│                        │ ┌──────────────────────────┐ │
│  LOGO                  │ │  HEADER BAR (56px)       │ │
│  ─────────             │ ├──────────────────────────┤ │
│  Nav items             │ │                          │ │
│                        │ │  PAGE CONTENT            │ │
│                        │ │  (scrolls independently) │ │
│                        │ │                          │ │
│  ─────────             │ │                          │ │
│  User profile          │ │                          │ │
└──────────────────────────────────────────────────────┘

Main content: margin-left 240px (sidebar width)
              min-height: 100vh
              background: var(--surface-raised)
              
Page content: max-width none (full bleed for tables)
              Padding: 0 (dashboard), 24px (settings, forms)
```

### Project Page Layout (Two-Panel)

```
┌─────────────────────────────────────────────────────────┐
│  Header bar with project breadcrumb                     │
├─────────────────────────────────────────────────────────┤
│  FOLDER PANEL (top)                                     │
│  height: 220px, scrollable-y, background white          │
│  border-bottom: 2px solid border-subtle                 │
├─────────────────────────────────────────────────────────┤
│  ANALYTICS STRIP (above table)                          │
│  height: 48px, horizontal metric chips                  │
├─────────────────────────────────────────────────────────┤
│  FILTER BAR                                             │
│  height: 52px, white, border-bottom                     │
├─────────────────────────────────────────────────────────┤
│  TASK TABLE (fills remaining height)                    │
│  scrollable-y, overflow-x: auto                         │
└─────────────────────────────────────────────────────────┘
```

---

## LANDING PAGE — FULL SPECIFICATION

### Navigation Bar

```
HEIGHT: 64px
Background: white / transparent (transitions to white on scroll)
Position: sticky top-0, z-index: 50
Border-bottom: none (when transparent), 1px solid border-subtle (on scroll)
Box-shadow: none → shadow-sm (on scroll)
Transition: all 200ms ease

LEFT:
  Logo (see Logo spec below)

CENTER (desktop only):
  How It Works  |  Features  |  Plans  |  Enterprise
  Font: font-body 500 15px text-secondary
  Hover: text-primary
  Active/current: text-primary, underline 2px brand-teal below

RIGHT:
  "Sign in" — ghost button
  "Start for Free" — accent button (brand-teal background)

MOBILE: hamburger icon, slide-in drawer
```

### Logo

```
WORDMARK: "CODUCTURA"
Font: Syne 800
Letter-spacing: 3px
Text-transform: uppercase
Size: 22px in nav, 28px on landing hero, 18px in sidebar

COLOR:
  On light backgrounds: var(--brand-navy)
  On dark backgrounds: white
  
ICON MARK (optional — use beside wordmark):
  Two overlapping rectangles suggesting a table/grid
  Left rectangle: solid brand-navy
  Right rectangle: brand-teal
  Slight overlap creates the "CO" feel
  Size: 28px × 28px in nav
```

### Hero Section

```
BACKGROUND: 
  Base: white
  Subtle radial gradient in top-right: 
    radial-gradient(ellipse 800px 600px at 80% 0%, rgba(14,165,201,0.06) 0%, transparent 70%)
  Very faint grid pattern overlaid:
    background-image: linear-gradient(var(--gray-100) 1px, transparent 1px),
                      linear-gradient(90deg, var(--gray-100) 1px, transparent 1px)
    background-size: 32px 32px
    opacity: 0.5

LAYOUT: Two columns (60/40 split), centered max-width 1280px, padding 120px 80px
Left column (60%):
  Eyebrow label:
    Text: "Execution Management Platform"
    Style: inline-flex badge — bg brand-teal-subtle, text brand-teal, 
           font-body 500 13px, padding 4px 14px, border-radius full
           Dot before text: 6px circle, background brand-teal, animate: pulse

  Headline (display-xl):
    Line 1: "Every Task."
    Line 2: "Every Decision."  
    Line 3: "Every Outcome."
    Color: brand-navy
    Last word of line 3 "Outcome": color brand-teal (accent word)
    Line height: 1.05
    Letter-spacing: -2.5px

  Subheadline (body-lg):
    "CODUCTURA is the execution platform that keeps your whole 
     organisation moving — with clear ownership, automatic escalation, 
     and zero lost decisions."
    Color: text-secondary
    Max-width: 480px
    Margin-top: 24px

  CTA group (margin-top: 40px):
    Primary: "Start for Free" — accent button, lg size
    Secondary: "Request a Demo" — secondary button, lg size, gap: 16px
    Below CTAs: "No credit card required · Setup in under 5 minutes"
      Font: font-body 400 13px, text-muted
      Margin-top: 16px

Right column (40%):
  App dashboard mockup screenshot / illustration
  Subtle drop shadow and slight rotation (-2deg) for depth
  Border-radius: var(--radius-xl)
  Border: 1px solid border-subtle
  Animate: float (translateY -8px ↔ 0, 4s ease-in-out, infinite)

SOCIAL PROOF BAR below hero:
  "Trusted by teams at..."
  Row of 5 company logos (greyscale), centered
  Separated by | 
  Font: font-body 400 14px text-muted "Trusted by teams at"
```

### How It Works Section

```
Background: var(--surface-raised)
Padding: 100px 80px
Max-width: 1280px, centered

SECTION HEADER (centered):
  Eyebrow: "Simple by design"
  Title: "Built for how execution actually works"
  Subtitle: "Three principles that eliminate the gap between planning and delivery."
  
THREE STEPS (horizontal, with connecting line):
Each step: width 33%, padding 40px

Step 1 — "Structure Your Work"
  Number: "01" — font-display 800 56px, text brand-teal, opacity 0.2
  Icon: FolderOpen, 28px, brand-teal
  Title: "Structure Your Work"
  Body: "Create projects, organise subfolders, and build your team hierarchy once. 
         Everything flows from structure — your tasks live exactly where they belong."

Step 2 — "Own Every Action"
  Number: "02"
  Icon: CheckSquare
  Title: "Own Every Action"
  Body: "Every task has an owner, a deadline, a type, and a status. Decisions and 
         blockers are tracked right inside the task row — nothing falls through the gaps."

Step 3 — "Nothing Gets Lost"
  Number: "03"
  Icon: ArrowUpCircle
  Title: "Nothing Gets Lost"
  Body: "Overdue decisions and stale blockers automatically escalate up the chain. 
         Your entire organisation sees what's moving, what's stuck, and why."

Connecting line between steps: 
  1px dashed line, brand-teal, 60% opacity
  Horizontal, centered vertically between step numbers
```

### Features Section

```
Background: white
Padding: 100px 80px

SECTION HEADER (left-aligned):
  Eyebrow: "Everything in one place"
  Title: "The platform your team will actually use"

FEATURE GRID: 2 columns, gap: 40px

Feature 1 — Table-First Architecture
  Icon: Grid3x3, 24px, brand-teal
  Title: "Table-First Architecture"
  Body: "All task logic lives inside rows. Create, update, and manage 
         tasks inline — no modals, no friction, no switching screens."

Feature 2 — Role-Based Clarity
  Icon: Users2
  Title: "Role-Based Clarity"
  Body: "Staff see their tasks. Managers see their teams. Directors see 
         everything. Permissions are automatic — based on your org hierarchy."

Feature 3 — Automatic Escalation
  Icon: ArrowUpCircle, color: brand-amber
  Title: "Automatic Escalation"
  Body: "When a decision deadline passes or a blocker goes stale, 
         the system escalates it automatically. No chasing. No surprises."

Feature 4 — File Integration
  Icon: Paperclip
  Title: "Connect Your Existing Files"
  Body: "Link files directly from SharePoint, Google Drive, Dropbox, 
         Notion, and more. Your files stay where they are. The reference lives 
         with the task."

Feature 5 — Deep Analytics
  Icon: BarChart3
  Title: "Analytics That Mean Something"
  Body: "Delay Index, Escalation Clusters, Repeated Blockers — real operational 
         metrics that tell you where your org is losing time, not just what's 
         overdue."

Feature 6 — Audit Everything
  Icon: ScrollText
  Title: "Full Audit Trail"
  Body: "Every action, status change, and decision is timestamped and logged. 
         Complete organisational memory — always."
```

### Social Proof / Testimonial Section

```
Background: var(--brand-navy)
Padding: 100px 80px
Color: white

Center layout, single large testimonial:
  Quote mark: " — font-display 800 120px, brand-teal, opacity: 0.2, 
               position: absolute, top-left
  Quote text: font-display 600 32px, text-inverse, max-width: 680px, 
              line-height: 1.3, centered
  Attribution: Name (font-body 500 16px, white), 
               Title + Company (font-body 400 14px, text-inverse-muted)
               Avatar: 48px circle, border: 2px solid rgba(255,255,255,0.2)
```

### Plans Section

```
Background: var(--surface-raised)
Padding: 100px 80px

SECTION HEADER (centered):
  Title: "Simple, predictable pricing"
  Subtitle: "Start free. Scale as you grow."
  Toggle: "Monthly / Annual" pill toggle (annual shows -20% badge)

3-COLUMN PRICING TABLE, centered, gap: 24px, max-width: 1000px

PLAN 1 — Starter
  Badge: none
  Price: "Free" (large)
  Subtext: "For small teams getting started"
  Features list (checkmark icons):
    ✓ Up to 3 team members
    ✓ 2 active projects
    ✓ Task table with all columns
    ✓ Basic analytics
    ✓ Email notifications
    ✗ Escalation system
    ✗ File integrations
    ✗ Advanced analytics
  CTA: "Get Started Free" — secondary button, full width

PLAN 2 — Professional (FEATURED)
  Badge: "Most Popular" — brand-teal pill, top-center of card
  Card style: border: 2px solid brand-teal, shadow-lg
  Scale: slightly larger (transform: scale(1.04))
  Background: white
  Price: "$18/user/mo" (billed annually)
  Subtext: "For growing teams that need accountability"
  Features list:
    ✓ Unlimited team members
    ✓ Unlimited projects
    ✓ Full task table + all columns
    ✓ Escalation system (auto + manual)
    ✓ Decisions & Blockers screen
    ✓ File integrations (all platforms)
    ✓ Advanced analytics + Delay Index
    ✓ Data export (CSV + PDF)
    ✓ Audit log
    ✓ Priority support
  CTA: "Start Free Trial" — accent button, full width

PLAN 3 — Enterprise
  Badge: none
  Price: "Custom" (large)
  Subtext: "For organisations that need full control"
  Features:
    ✓ Everything in Professional
    ✓ Supreme Admin visibility layer
    ✓ BigQuery + Looker Studio analytics
    ✓ Custom SSO integration
    ✓ Dedicated onboarding
    ✓ SLA + compliance docs
    ✓ Custom data retention policies
  CTA: "Contact Sales" — secondary button, full width
```

### CTA Banner

```
Background: brand-navy
Padding: 80px
Centered

Title: "Stop managing. Start executing."
  Font-display 700 48px, white, letter-spacing -1px
  
Subtitle: "Join teams who've replaced the chaos of missed 
           decisions and forgotten blockers with CODUCTURA."
  Font-body 400 18px, text-inverse-muted, max-width: 480px, centered

CTAs (gap: 16px, centered):
  "Start for Free" — accent button, lg
  "See a Demo" — ghost button on dark (text white, border white/20)
```

### Footer

```
Background: var(--gray-900)
Color: text-inverse
Padding: 64px 80px 40px

4-COLUMN LAYOUT:
  Col 1: Logo + tagline + social icons (LinkedIn, Twitter, GitHub)
  Col 2: Product (Features, How It Works, Plans, Changelog)
  Col 3: Company (About, Careers, Press, Contact)
  Col 4: Legal (Privacy Policy, Terms of Service, Security)

Bottom bar (border-top 1px solid rgba(255,255,255,0.08), padding-top 24px):
  Left: "© 2025 CODUCTURA. All rights reserved."
  Right: "Made for teams who execute."
  Font: font-body 400 13px, text-muted
```

---

## APP SCREENS — FULL SPECIFICATION

### Register Flow (/register)

```
LAYOUT: Centered, max-width 480px, margin: auto, padding: 80px 24px
Background: var(--surface-raised)

LEFT SIDE PANEL (desktop — 2 column layout):
  Left: 420px — dark panel, background brand-navy
    Top: Logo (white)
    Middle: Benefits list
      "Why teams choose CODUCTURA"
      ✓ Full task ownership with automatic timestamps
      ✓ Decisions and blockers tracked per task
      ✓ Escalation when deadlines slip
      ✓ Analytics your director will actually open
      ✓ File links from SharePoint, Drive, Dropbox
    Bottom: Testimonial quote (brief)
  Right: Form panel

PROGRESS INDICATOR:
  Steps: "Company" → "Your Account" → "Confirm"
  Style: horizontal stepper
  Step circle: 28px, border 2px solid border-default
  Active: filled brand-navy, text white
  Completed: filled brand-teal, checkmark icon
  Connecting line: 1px solid border-default

STEP 1 — Company:
  Title: "Set up your company" (h2)
  Subtitle: "This creates your organisation's workspace." (text-secondary)
  Fields: Company Name, Company Type (dropdown), Industry (dropdown), Company Domain
  CTA: "Continue →" (accent button, full width)

STEP 2 — Your Account:
  Title: "Create your account"
  Fields: Admin Email, Password (with show/hide toggle), Role, Name of Position
  Domain validation notice: 
    "Your email must match [domain.com]" 
    Style: info banner, background brand-teal-subtle, icon: Info
  CTA: "Create Account →"

STEP 3 — Confirm:
  Summary of entered details in read-only list
  Terms checkbox: "I agree to the Terms of Service and Privacy Policy"
  CTA: "Launch your workspace" (accent button)

SIGN IN LINK: "Already have an account? Sign in" — centered, below form
```

### Login Page (/login)

```
Same split layout as register

RIGHT PANEL (form side):
  Logo centered at top
  Title: "Welcome back" (h2, centered)
  Subtitle: "Sign in to your workspace" (text-secondary, centered)
  
  Fields: Email, Password (with show/hide)
  "Forgot password?" link — right-aligned, font-body 500 13px text-accent
  
  "Sign In" — primary button, full width
  
  Divider: "— or —" (text-muted, font 13px)
  
  "Register your company" link — centered

ERROR STATE:
  Banner above form (not below inputs):
    Background: color-danger-bg
    Border: 1px solid color-danger
    Border-radius: radius-md
    Icon: AlertCircle, color-danger
    Text: "Invalid email or password. Please try again."
```

### Onboarding Checklist (post-register)

```
Full-page centered layout, max-width: 640px

Header:
  "Welcome to CODUCTURA, [Company Name]" — h1
  "Let's set up your workspace in 4 steps." — body-lg text-secondary

CHECKLIST CARD:
  Background: white, border, border-radius: radius-xl, shadow-md
  Padding: 32px 40px

Steps (vertical list):
  ─────────────────────────────────
  [✓] Step 1: Invite your team
      "Invite team members and assign their roles"
      Status: Completed (green checkmark)
      
  [ ] Step 2: Create a department
      "Set up your org structure"
      CTA: "Create Department" button (sm)
      
  [ ] Step 3: Create your first project
      CTA: "Create Project" button (sm)
      
  [ ] Step 4: Configure column visibility
      "Decide which task columns your org needs"
      CTA: "Go to Settings" button (sm)
  ─────────────────────────────────

Progress bar: thin (4px), brand-teal fill, below steps
"{N} of 4 steps complete"

"Skip for now" — text link, text-muted, bottom-center
```

### Main Dashboard (/dashboard)

```
PAGE LAYOUT:
  No page padding — analytics bar and project grid are full-bleed

ANALYTICS BAR (horizontal scroll, full width):
  Background: white
  Height: auto (cards ~88px + 20px padding top/bottom)
  Border-bottom: 1px solid border-subtle
  Overflow-x: auto, scrollbar hidden
  Padding: 20px 24px
  Display: flex, gap: 12px

  Cards layout: see Metric Card spec above
  
  Role-based card groupings separated by thin vertical dividers

BELOW ANALYTICS BAR:
  Padding: 24px
  
  SECTION HEADER:
    Left: "Projects" h2
    Right: "New Project" accent button (sm)
  
  PROJECTS GRID:
    display: grid
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr))
    gap: 20px
    margin-top: 16px
  
  PROJECT CARD (see Card spec above):
    Entire card clickable → /dashboard/projects/[projectId]

EMPTY STATE (no projects):
  Centered in projects area, padding: 80px
  Illustration: simple geometric grid/table icon in brand-teal tint
  Title: "No projects yet"
  Subtitle: "Create your first project to start tracking tasks."
  CTA: "Create Your First Project" — accent button
```

### Project View (/dashboard/projects/[projectId])

```
HEADER BAR (extends the app header):
  Breadcrumb: Dashboard > Projects > [Project Name]
  Right actions: 
    "Add Folder" ghost button
    "New Task" accent button

FOLDER PANEL (220px height, white):
  Scrollable vertically
  Left-aligned tree view
  
  Root: Project name (h4, bold, with FolderOpen icon)
  Children: Subfolders with indentation (20px per level)
  Each folder item:
    Height: 36px
    Padding-left: depends on depth (16px + 20px × depth)
    Icon: Folder (closed) / FolderOpen (active) 16px
    Name: font-body 400 14px
    Task count badge: gray pill on right
    Hover: background gray-50, name text-primary
    Active: background brand-teal-subtle, text brand-teal, 
            icon brand-teal, bold
  
  Add Subfolder:
    Below each folder on hover: "+ Subfolder" ghost link (13px, text-muted)
  
  File indicator: Paperclip icon (12px, text-muted) if folder has files
  
  FOLDER CONTEXT MENU (right click):
    Rename, Add Subfolder, Upload Files, Delete
    (uses Dropdown Menu component)

ANALYTICS STRIP (48px, white, border-bottom):
  Horizontal row of metric chips
  Chip: "Open: 12" / "Overdue: 3" / "LRT: 1" / "Delay: 8%" / 
        "Blockers: 2" / "Decisions: 4"
  Style: font-body 500 13px, inline-flex, gap 6px
  Number color: matches metric color from analytics system
  Separator: | character in text-muted

FILTER BAR (52px, white, border-bottom):
  Padding: 0 16px
  Display: flex, gap: 8px, align-items: center
  
  "Filters:" label — font-body 500 12px text-muted
  Filter dropdowns (compact, 32px height each):
    Owner | Status | Decision | Blocker | Task Type | Date Range
  
  Right side:
    "Overdue Only" toggle chip
    Separator |
    Active filter count: "3 active" badge in brand-teal
    "Clear all" ghost link

TASK TABLE: See Table component spec above
```

### Decisions & Blockers Screen (/dashboard/decisions)

```
HEADER:
  Title: "Decisions & Blockers" h1
  Subtitle: "Track open decisions and blockers across all projects." text-secondary
  Right: Filter controls

FILTER BAR (full-width, white card):
  Row of filter dropdowns + toggle chips:
    View: "All" / "Escalated" / "Auto-Escalated" / "Manually Escalated"
    Status: Decision Pending / Blocker Open / Both
    Owner: searchable dropdown
    Deadline: overdue / upcoming / all
    Date range picker
    Project: searchable dropdown

CONTENT: Two tabs

TAB 1 — Decisions
  Table: Task ID | Description | Project | Decision Owner | Decision Deadline | Status | Escalated
  Row colors: overdue deadline → danger-bg tint left border
  Escalated badge in status column

TAB 2 — Blockers
  Table: Task ID | Description | Project | Blocker Status | Blocker Description | Owner | Deadline
  Same row treatment

ESCALATION GROUPS (expandable section at top if groups exist):
  Grouped card for each escalation group:
    Title: group name, bold
    Count badge: "8 tasks" 
    Escalation info: "Escalated by [Name] on [date]" text-muted
    "Escalated to: [Name, Role]" text-secondary
    Expand button: chevron, shows nested task list
    Nested groups indented, same treatment
```

### Settings (/settings)

```
LAYOUT: 
  Left sidebar: 200px, settings navigation
  Right content: scrollable form area, max-width 720px, padding 32px

SETTINGS SIDEBAR:
  Background: white, border-right 1px solid border-subtle
  Nav items (same style as app sidebar but light):
    Company
    Users
    Departments
    Integrations
    Column Visibility
    Audit Log

────────────────────
SETTINGS: Company
  Title: "Company Settings"
  
  FORM SECTION (card):
    Title + border-bottom
    Fields: Company Name, Domain (read-only, greyed), Industry (dropdown)
    Save button bottom-right
    
────────────────────
SETTINGS: Users

  INVITE SECTION (card at top):
    Title: "Invite Team Member"
    Inline form row: Email input | Role dropdown | Department dropdown | Manager dropdown | Invite button
    
  MEMBERS TABLE:
    Columns: Name | Position | Role | Department | Manager | Status | Actions
    Actions: Edit (pencil icon), Deactivate/Reactivate (toggle), Transfer Admin (crown icon)
    Status: Active (green badge) / Inactive (gray badge)
    
  ROLE EDIT INLINE:
    Click Edit → row expands with inline dropdowns for Role, Department, Manager
    Save / Cancel inline buttons

────────────────────
SETTINGS: Departments

  CREATE DEPARTMENT (card):
    Name input | Department Head dropdown | "Create" button
    
  DEPARTMENTS TABLE:
    Columns: Department Name | Head | Member Count | Actions
    
  ORG HIERARCHY TREE VIEW:
    Interactive expandable tree
    Same visual style as folder panel but uses Building2 + UserCircle icons
    Director at root, departments as first level, etc.
    Each node: name + role badge + member count

────────────────────
SETTINGS: Integrations

  SECTION HEADER: "Connected File Platforms"
  Subtitle: "Connect platforms to link files directly from task rows."
  
  PLATFORM CARDS (2-column grid):
    Each platform card:
      Logo/icon (32px)
      Platform name (font-body 500 15px)
      Description (font-body 13px text-muted)
      Status: "Connected" badge (success) or "Not Connected" (muted)
      CTA: "Connect" (accent button sm) or "Disconnect" (danger ghost sm)
      Last used: "Last used: 2 days ago" (text-muted 12px, if connected)
    
    Platforms:
      Microsoft SharePoint | Microsoft OneDrive | Google Drive
      Dropbox | Box | Confluence | Notion

────────────────────
SETTINGS: Column Visibility

  Info banner: "Changes apply to all members in your organisation."
  
  COLUMNS TABLE:
    Column: Col # | Column Name | Always visible | Hideable | Current status toggle
    Columns 1-5: "Always visible" badge, toggle disabled
    Columns 6,8,11-17: Toggle switch (on/off)
    Toggle: 40px × 22px, brand-teal when on, gray when off

────────────────────
SETTINGS: Audit Log

  FILTER BAR:
    User dropdown | Action type dropdown | Entity type | Date range
    
  AUDIT TABLE:
    Columns: Timestamp | User | Action | Entity | Details
    Timestamp: font-mono 12px text-muted
    Action: colored badge matching action type
    Details: truncated JSON diff with "View" link
    Expandable row: shows before/after JSON diff in code style
    
  No editing controls — read-only view
```

### Analytics Dashboard (drill-down, per role)

```
ACCESSIBLE FROM: clicking metric cards on dashboard

HEADER:
  Breadcrumb showing drill-down path
  "Viewing: [Name]'s analytics" or "Viewing: [Department] analytics"
  Date range picker (right)

METRICS SUMMARY ROW:
  Large metric cards (6 in a row):
  Open | Completed | Overdue | Long-Running | Escalations | Delay Index
  Each: large number (font-display 700 36px), label, trend vs previous period

CHARTS ROW:
  Left 65%: Line chart (completion rate over time, Recharts)
    Multi-line for team members (each a different color)
    Smooth curves, no dots unless hovered
    Hover: vertical line + tooltip with all values
    
  Right 35%: Donut chart (task status distribution)
    Legend below, clickable to filter
    Center label: "Total Tasks: N"

DETAILS TABLE:
  For drill-down: table of team members / departments
  Each row: avatar + name | open | overdue | escalations | completion rate | delay index
  Sortable columns
  Click row → drill down one level
```

### Supreme Admin (/admin)

```
VISUAL DIFFERENTIATION:
  Sidebar accent color: brand-amber instead of brand-teal
  Header banner: 3px top border of brand-amber
  Small "Admin Mode" badge in header: amber pill

DASHBOARD:
  Top metrics row (4 large cards):
    Total Companies | Total Active Users | Total Tasks (all orgs) | Avg Delay Index

  COMPANIES TABLE:
    Columns: Company | Users | Active Tasks | Delay Index | Decision Latency | Overdue % | Last Activity | Actions
    Action: "Inspect" button (amber, opens Inspector View)
    Sort by any column
    Red highlight row: orgs with delay index > 25%
    
  ANALYTICS PANEL (Recharts):
    Bar chart: Task Volume by Org (clickable bars)
    Scatter plot: Delay Index vs Decision Latency (each dot = one org)
    Line chart: Cross-company completion trends over time

COMPANY INSPECTOR VIEW:
  Full-page overlay (or new route /admin/orgs/[orgId])
  
  INSPECTOR BANNER (top, full-width):
    Background: brand-amber + white gradient
    Left: Building2 icon, "Inspecting: [Company Name]" bold
    Right: "Read-Only Mode" badge, "Exit Inspector" button
  
  Below banner: full org dashboard loaded in read-only
  All interactive elements (edit, delete, save) are hidden/disabled
  Table cells not editable (click does nothing)
  
  Read-only indicator: subtle orange tint on all table cells
  Tooltip on hover: "View only — you are in Inspector Mode"

GUIDANCE NOTE COMPOSER:
  Floating panel (position: fixed, bottom-right)
  Title: "Add Guidance Note"
  Textarea: "Write a note visible to this org's Director and Admin..."
  Target: "[Company Name]'s Dashboard" (read-only)
  "Post Note" amber button
  Posted notes shown in list below, with delete option
```

---

## MICRO-INTERACTIONS & ANIMATIONS

```
PAGE TRANSITIONS:
  Fade + slide (12px Y) over 200ms, ease-out
  On route change via Next.js layout transitions

TABLE ROW ADD:
  New row slides in from top: translateY(-8px) → 0, fade in, 200ms, spring

TABLE ROW DELETE:
  Slide out left + fade: translateX(-16px), opacity 0, 200ms
  Row above/below smoothly fills gap

STATUS BADGE CHANGE:
  Scale to 0.9 → 1.05 → 1 over 200ms when value changes
  Color fade transition 150ms

METRIC CARD NUMBERS:
  Count-up animation on load (if value > 0)
  Duration: 800ms, ease-out
  Only on first render per session

SIDEBAR NAV ACTIVE STATE:
  Animated left border slides in from top: scaleY 0 → 1, 180ms
  Background fade in 150ms

ESCALATION BADGE:
  Pulse animation on nav badge when new escalation arrives:
  box-shadow: 0 0 0 4px rgba(245,158,11,0.2), infinite 2s

PROGRESS BAR:
  Width animates on mount: 0 → actual%, 600ms, ease-out

MODAL:
  Enter: scale(0.95) + opacity(0) → scale(1) + opacity(1), 200ms spring
  Exit: scale(0.97) + opacity(0), 150ms ease-in

FILTER CHIPS:
  Appear with scale(0.8) → scale(1), 150ms spring

DROPDOWN:
  Enter: translateY(-6px) + opacity(0) → translateY(0) + opacity(1), 150ms
  
TOOLTIPS:
  Fade in over 100ms, delay 400ms on initial hover
  Instant fade out

LOADING STATES:
  Skeleton shimmer (see earlier spec)
  Button loading: spinner replaces text, button width locked
  Table loading: 5 skeleton rows, correct column widths

ERROR SHAKE:
  On invalid form submit: translateX -4px → 4px → -2px → 2px → 0
  Duration: 300ms, ease-in-out
  Applied to the field or form section
```

---

## EMPTY STATES

```
Each empty state has:
  Illustration: geometric/minimal SVG, brand-teal tint on light gray
  Title: Clear, human ("No tasks yet")
  Subtitle: Actionable ("Create your first task to start tracking work")
  CTA button when appropriate

Specific states:
  No projects → "Create your first project"
  No tasks in folder → "Add your first task"
  No escalations → "Nothing escalated. Things are moving!" (success tone)
  No notifications → "You're all caught up"
  No search results → "No results for '[query]'"
  No team members → "Invite your first team member"
  No audit log entries → "No activity recorded yet"
  Empty analytics → "No data for this period"
```

---

## ERROR STATES & VALIDATION

```
FORM VALIDATION:
  Real-time: validate on blur (not while typing)
  Error message: below field, font-body 400 13px color-danger
  Icon: AlertCircle 14px before text
  Field border: color-danger
  
GLOBAL ERROR BANNER:
  Full-width, below header
  Background: color-danger-bg
  Border-bottom: 2px solid color-danger
  Padding: 12px 24px
  Icon: XCircle 18px
  Text: message
  Dismiss: X button right

404 PAGE:
  Large "404" in font-display 800 120px, color gray-200
  "Page not found" in h2
  "The page you're looking for doesn't exist or has been moved."
  "Back to Dashboard" button

500 PAGE:
  Same structure
  "Something went wrong on our end. We're on it."
  "Refresh Page" + "Back to Dashboard"
```

---

## RESPONSIVE BEHAVIOR

```
BREAKPOINTS:
  sm:  640px
  md:  768px
  lg:  1024px
  xl:  1280px
  2xl: 1440px

MOBILE (< 768px):

Landing page:
  Single column layout
  Hero: headline 40px, single CTA
  Pricing: stacked cards, full-width
  Features: 1 column

App (≤ 768px):
  Sidebar: hidden, accessed via hamburger bottom navigation bar
  Bottom nav: 5 icons — Dashboard, Projects, Decisions, Settings, Profile
  Analytics bar: horizontal scroll, cards slightly narrower (160px)
  Task table: horizontal scroll, locked Task ID + Description columns, 
              other columns scrollable
  Modals: full-screen bottom sheet (slide up animation)
  Filter bar: collapsed behind "Filter" button, opens slide-down panel

TABLET (768px–1024px):
  Sidebar: collapsed (56px, icons only), expands on hover
  Project cards: 2-column grid
  Analytics bar: same as desktop
```

---

## ACCESSIBILITY

```
COLOR CONTRAST:
  All text on white backgrounds: minimum 4.5:1 ratio
  Large text (18px+ or 14px+ bold): minimum 3:1 ratio
  brand-navy on white: 15:1 ✓
  brand-teal on white: 3.1:1 (use only for large text or decorative)
  text-secondary (#475569) on white: 7.5:1 ✓

FOCUS STATES:
  Every interactive element has visible focus ring
  Focus ring: 2px solid brand-teal, 2px offset
  Never suppress outline without replacement

KEYBOARD NAVIGATION:
  Tab order: logical, top-left to bottom-right
  Escape closes modals/dropdowns
  Enter activates buttons/links
  Arrow keys navigate dropdown items, table rows
  Ctrl+K opens command palette

ARIA:
  All icon-only buttons have aria-label
  Tables have proper thead/tbody, scope attributes
  Status badges have role="status"
  Loading states have aria-busy="true"
  Modals trap focus, restore on close
  Live regions for notifications

SCREEN READER:
  Status changes announced via aria-live="polite"
  Error messages linked to inputs via aria-describedby
  Tables with sortable columns: aria-sort attribute
```

---

## PRINT / EXPORT STYLES

```
When generating PDF exports (analytics, task tables):

  Background: white
  Remove: sidebar, header, buttons, filters
  Show: company logo top-left, "CODUCTURA" top-right, export date
  Table: compact, 13px font, no hover states
  Page break: before each major section
  Footer: page number, company name, "Generated on [date]"
  
  Color: preserve status badge colors (use !important)
  Charts: render as static PNG before PDF generation (via Puppeteer screenshot)
```

---

## COPY STRINGS — FULL REFERENCE

```
NAVIGATION:
  Dashboard        "Dashboard"
  Projects         "Projects"
  Decisions        "Decisions & Blockers"
  Settings         "Settings"
  Admin            "Admin Console"
  Sign out         "Sign Out"

TASK STATUS LABELS:
  not_started      "Not Started"
  in_progress      "In Progress"
  blocked          "Blocked"
  cancelled        "Cancelled"
  completed        "Completed"
  reopened         "Reopened"
  escalated        "Escalated"

TASK TYPE LABELS:
  mini             "Mini  ·  ≤ 30 min"
  small            "Small  ·  30 min – 2 h"
  medium           "Medium  ·  2 – 4 h"
  day              "Day  ·  4 – 8 h"
  long_running     "Long Running  ·  Ongoing"

OWNERSHIP TYPE:
  fully_owned      "Fully Owned"
  influenced       "Influenced"
  dependent        "Dependent"

BLOCKER STATUS:
  none             (no badge)
  open             "Blocker Open"
  resolved         "Blocker Resolved"

DECISION STATUS:
  pending          "Decision Pending"
  resolved         "Decision Resolved"

ESCALATION MESSAGES:
  auto decision    "Decision deadline passed — escalated automatically"
  auto blocker     "Blocker unresolved for [N] days — escalated automatically"
  manual           "Manually escalated by [Name]"
  to role          "Escalated to: [Name] ([Role])"

EMPTY STATES:
  no projects      "No projects yet · Create your first project to start tracking tasks"
  no tasks         "No tasks in this folder · Click + Add Task to create your first task"
  no escalations   "Nothing escalated · Your team is on top of things"
  no notifications "You're all caught up · No new notifications"
  no results       "No results · Try adjusting your filters or search term"

CONFIRMATION DIALOGS:
  delete task      "Delete this task? This action cannot be undone."
  deactivate user  "Deactivate [Name]? They will lose access to the workspace."
  escalate group   "Escalate these [N] tasks to [Name]? They will be notified immediately."

TOOLTIPS (on hover, column headers):
  Task ID          "Auto-generated unique task identifier"
  Ownership Type   "How this person relates to the task"
  Decision Required "Does this task need a decision before completion?"
  Blocker          "Is something preventing this task from progressing?"
  Delay Index      "Overdue tasks as a % of total tasks. Lower is better."
  Long Running     "Tasks with indefinite duration — monitor closely"
```

---

## FINAL IMPLEMENTATION NOTES

1. **Use CSS custom properties everywhere.** Never hardcode hex or pixel values in components.

2. **Build the design system first** before any screen. Create a `/src/styles/` folder with:
   - `tokens.css` — all CSS variables above
   - `typography.css` — all type classes
   - `animations.css` — all keyframes
   Import all in `globals.css`.

3. **Component order to build:**
   Button → Input → Badge → Card → Dropdown → Modal → Table → Sidebar → all Pages

4. **Dark mode:** Not in scope for v1. CSS variables are structured to support it 
   in the future (surface/text tokens abstract the colors). Do not add dark mode 
   complexity now — focus on light mode done perfectly.

5. **Loading performance:** All fonts use `display=swap`. 
   Images use `next/image`. Tables use virtualisation.
   Analytics charts lazy-load. Skeleton states always before real content.

6. **Syne font fallback:** `'Syne', 'Georgia', serif` — if Syne fails to load,
   Georgia gives a similar authoritative quality.

7. **The one rule:** When in doubt, add space. Dense UIs that feel cramped lose 
   user trust. A task management platform where users spend hours must feel calm.

---

*End of CODUCTURA Design System. Implement from design tokens first, then components, 
then screens, in the order listed. Every decision here serves the goal: a platform 
that feels serious, trustable, smart, and psychologically comforting to use.*
