# Sai Prakash Studio design system

Version 1.2. Generated from the same source as the page at https://saiprakash.design, so it can't drift from what you see there.

## Use it with an agent

Give a model the prompt at the end of this file, then a brief. It answers with one JSON screen built only from the components below. The page's Studio compiles that JSON and grades it with the nine checks listed here.

## Color

| Token | Light | Dark | Role |
|---|---|---|---|
| `--paper` | #EAEDF7 | #0E1233 | Page background |
| `--paper-2` | #F5F6FC | #151A45 | Raised surface |
| `--card` | #FFFFFF | #1C2257 | Cards and dialogs |
| `--ink` | #12163A | #ECEBF7 | Primary text |
| `--ink-2` | #4B5180 | #A2A7D0 | Secondary text |
| `--line` | #C6CBE6 | #2B3268 | Hairlines and borders |
| `--indigo` | #2E3BC4 | #9CA8FF | Links, focus, what machines read |
| `--indigo-wash` | #D9DDF6 | #1D2460 | Machine-layer surface |
| `--haldi` | #F5B82E | #F4B731 | Highlight: what a person should notice |
| `--haldi-wash` | #F7D681 | #6B531A | Soft highlight |
| `--haldi-ink` | #8A5A00 | #F4B731 | Highlight text and labels |
| `--kumkum` | #B8322A | #FF8A78 | Danger and failure |

## Type

Set in rem, so it follows the reader's text size.

| Role | Token | Size | Face |
|---|---|---|---|
| hero | `--fs-hero` | `clamp(2.5rem,6.4vw,5.5rem)` | Eczar 600 |
| title | `--fs-2xl` | `clamp(1.875rem,3.3vw,2.75rem)` | Eczar 500 |
| rule | `--fs-xl` | `clamp(1.375rem,2.2vw,1.875rem)` | Eczar 500 |
| stat | `--fs-stat` | `clamp(2.75rem,4.6vw,4rem)` | Eczar 700 |
| lead | `--fs-l` | `clamp(1.0625rem,1.2vw,1.1875rem)` | Hanken Grotesk 400 |
| body | `--fs-m` | `1rem` | Hanken Grotesk 400 |
| small | `--fs-s` | `.875rem` | Hanken Grotesk 400 |
| label | `--fs-xs` | `.71875rem` | JetBrains Mono 500 |

## Space and radius

Space: 4, 8, 12, 16, 24, 32, 48, 64, 96, 128 px.

Radius: s 8 px, m 12 px, l 18 px, pill fully round.

## Voice

- Plain words, active voice.
- No exclamation marks and no emoji.
- Buttons say what happens, in four words or fewer.

## Components

### Screen

One screen holds one to three Sections.

No props.

Takes children.

### Section

One idea per section. The label names it, the title says it.

Props: `label?` (text, 5 words max), `title?` (text).

Takes children.

```json
{"type":"Section","label":"Case file","title":"Measure the output, not the demo.","children":[{"type":"Text","text":"One idea per section, stated in the title.","tone":"muted"}]}
```

### Heading

Headings sit inside a Section and never skip a level.

Props: `text` (text).

```json
{"type":"Section","title":"A section title","children":[{"type":"Heading","text":"A heading inside it"},{"type":"Text","text":"Then the paragraph it introduces."}]}
```

### Text

Short paragraphs, one idea each.

Props: `text` (text), `tone?` (default | muted), `size?` (m | l).

```json
{"type":"Text","text":"People read design systems. Now agents read them too.","size":"l"}
```

### Label

Labels are mono, upper case, five words at most.

Props: `text` (text, 5 words max).

```json
{"type":"Label","text":"Case files"}
```

### Stack

Stack things that are read top to bottom.

Props: `gap?` (s | m | l).

Takes children.

```json
{"type":"Stack","gap":"s","children":[{"type":"Text","text":"First line."},{"type":"Text","text":"Second line.","tone":"muted"}]}
```

### Row

Put actions or chips that belong together in one row.

No props.

Takes children.

```json
{"type":"Row","children":[{"type":"Button","text":"Book a call","variant":"primary"},{"type":"Button","text":"Read the notes","variant":"ghost"}]}
```

### Grid

A grid holds items of equal weight. It stacks on phones.

Props: `cols?` (2 | 3 | 4).

Takes children.

```json
{"type":"Grid","cols":2,"children":[{"type":"Stat","value":"83%","caption":"less time per task"},{"type":"Stat","value":"78%","caption":"less time per document"}]}
```

### Card

A card sets one thing apart. Not everything is a card.

Props: `title?` (text), `tone?` (plain | raised).

Takes children.

```json
{"type":"Card","title":"Deep cut","tone":"raised","children":[{"type":"Text","text":"Architecture, data and who built what.","tone":"muted"}]}
```

### Stat

A big number always says what it counts.

Props: `value` (text), `caption` (text), `label?` (text).

```json
{"type":"Stat","label":"PromptForge","value":"78%","caption":"less time per document"}
```

### Button

One primary action per section. The text says what happens.

Props: `text` (text, 4 words max), `variant?` (primary | ghost).

```json
{"type":"Row","children":[{"type":"Button","text":"Start the tour","variant":"primary"},{"type":"Button","text":"Skip for now","variant":"ghost"}]}
```

### Chip

A chip states a status in words, never by color alone.

Props: `text` (text), `tone?` (neutral | live | win).

```json
{"type":"Row","children":[{"type":"Chip","text":"Shipped","tone":"win"},{"type":"Chip","text":"In build","tone":"live"},{"type":"Chip","text":"Draft"}]}
```

### Sutra

The one-line rule. Fourteen words at most.

Props: `text` (text, 14 words max).

```json
{"type":"Sutra","text":"Give the agent twelve kilobytes first."}
```

### Quote

Quote a person, with their role.

Props: `text` (text), `cite?` (text).

```json
{"type":"Quote","text":"If an agent keeps breaking a rule, read the rule again.","cite":"Notes, October 2026"}
```

### List

Lists hold two to eight parallel items.

Props: `items` (list of text), `ordered?` (true or false).

```json
{"type":"List","items":["Name a set once.","State the rule in one line.","Test that the agent followed it."]}
```

### Steps

Steps show a sequence. Mark the step that matters.

Props: `items` (list of text), `key?` (number, 0-based).

```json
{"type":"Steps","items":["Brief","Write","Check","Fix"],"key":2}
```

### Bars

Bars share one scale that starts at zero.

Props: `items` (list of {name, value}), `unit?` (text), `label?` (text).

```json
{"type":"Bars","label":"Minutes per document","unit":"min","items":[{"name":"Before","value":90},{"name":"After","value":20}]}
```

### Strings

The signature headline. Up to three lines of 24 characters.

Props: `lines` (list of text).

```json
{"type":"Strings","lines":["Built for people.","Read by agents."]}
```

### Field

Every field has a visible label.

Props: `label` (text), `placeholder?` (text), `kind?` (text | email).

```json
{"type":"Field","label":"Email","placeholder":"you@example.com","kind":"email"}
```

### Divider

The double danda ends a section, the way it ends a verse.

No props.

```json
{"type":"Stack","gap":"s","children":[{"type":"Text","text":"The end of a section.","tone":"muted"},{"type":"Divider"}]}
```

## Checks

1. Valid JSON
2. Only system components
3. No raw styling or unknown props
4. Required content present
5. One primary action per section
6. Headings in order (WCAG 1.3.1)
7. Every field has a label (WCAG 3.3.2)
8. Copy follows the voice
9. Numbers are real

## Agent prompt

```text
You are a UI agent for the "Sai Prakash Studio" design system. Turn the visitor's brief into one screen built only from the components below.

OUTPUT
Return one JSON object and nothing else: no prose and no markdown fences.
Shape: {"type":"Screen","children":[ ...Section nodes ]}
Each node is {"type":"<Component>", ...its props, "children":[...]}. Props sit directly on the node. Only components marked [children] take children.

COMPONENTS
- Screen() [children]: One screen holds one to three Sections.
- Section(label?: text (5 words max), title?: text) [children]: One idea per section. The label names it, the title says it.
- Heading(text: text): Headings sit inside a Section and never skip a level.
- Text(text: text, tone?: "default"|"muted", size?: "m"|"l"): Short paragraphs, one idea each.
- Label(text: text (5 words max)): Labels are mono, upper case, five words at most.
- Stack(gap?: "s"|"m"|"l") [children]: Stack things that are read top to bottom.
- Row() [children]: Put actions or chips that belong together in one row.
- Grid(cols?: 2|3|4) [children]: A grid holds items of equal weight. It stacks on phones.
- Card(title?: text, tone?: "plain"|"raised") [children]: A card sets one thing apart. Not everything is a card.
- Stat(value: text, caption: text, label?: text): A big number always says what it counts.
- Button(text: text (4 words max), variant?: "primary"|"ghost"): One primary action per section. The text says what happens.
- Chip(text: text, tone?: "neutral"|"live"|"win"): A chip states a status in words, never by color alone.
- Sutra(text: text (14 words max)): The one-line rule. Fourteen words at most.
- Quote(text: text, cite?: text): Quote a person, with their role.
- List(items: list of text, ordered?: true or false): Lists hold two to eight parallel items.
- Steps(items: list of text, key?: number, 0-based): Steps show a sequence. Mark the step that matters.
- Bars(items: list of {name, value}, unit?: text, label?: text): Bars share one scale that starts at zero.
- Strings(lines: list of text): The signature headline. Up to three lines of 24 characters.
- Field(label: text, placeholder?: text, kind?: "text"|"email"): Every field has a visible label.
- Divider(): The double danda ends a section, the way it ends a verse.

RULES
1. The top level holds only Sections, one to three of them.
2. One primary Button per Section. Every other Button uses variant "ghost".
3. Headings sit inside a Section.
4. Every Field has a label. A placeholder is not a label.
5. Never add colors, sizes, fonts, CSS, HTML or any prop that isn't listed. The system applies its own tokens.
6. Voice: plain words, active voice, no exclamation marks, no emoji. Buttons say what happens in four words or fewer. Never "Submit", "Click here" or "Learn more".
7. Sutra: fourteen words at most. Strings: up to three lines of 24 characters each. Lists: two to eight items.
8. Stat values contain a number. Bars values are numbers of zero or more.
9. Write specific, realistic content for the brief, and keep it short.
```
