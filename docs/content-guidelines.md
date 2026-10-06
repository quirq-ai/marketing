# quirq content guidelines

The rules every piece of quirq marketing content meets before it ships, and the
checklist that proves it. "Content" means anything published under the quirq
name: posts, essays, launch copy, social cards, figures, images, video and
brand assets.

This repo is also the reusable media library. Anything that passes the
checklist lands in the layout described below, so the next post, deck or page
can pick it up instead of redrawing it.

Status: **draft**. Sources these rules were drawn from are listed at the end;
anything marked _(proposed)_ is new and open for review.

---

## 1. Principles

1. **Every claim is traceable.** A number, quote or result names the note,
   paper or dataset it came from. If the source does not carry it, the content
   does not either.
2. **Derive, never invent.** Copy and figures are generated from a source, not
   written beside it. Never invent a datum to complete a picture, a sentence or
   a chart.
3. **Say what did not survive.** When a later study overturned an earlier
   headline, the piece says so rather than quoting the number that did not
   hold.
4. **Say what was cut.** A summary of a longer list or table says it is a
   summary. Silent truncation reads as the whole thing.
5. **No fake signals.** No invented metrics, customer names, integrations,
   logos or testimonials. A supported ecosystem is not a customer. Keep
   qualifiers such as "illustrative" or "sample" wherever the source has them.
6. **One asset, one record.** A title, date or reading time lives in exactly
   one index entry and everything else reads it from there, so it can never
   disagree with itself.

## 2. Voice and tone

quirq writes like a careful engineer explaining a measurement to a peer: plain,
specific and honest about what is and is not known.

| Do | Don't |
|---|---|
| Concrete nouns and verbs: "the agent re-read 41 files" | Generic tech claims: "unlock next-gen AI productivity" |
| State the result, then the qualifier | Bury the result under hedges |
| Short declarative sentences; vary rhythm deliberately | Strings of fragments or arrow chains |
| Argue and frame, citing the note | Introduce a figure the note does not carry |
| Admit a limit in one sentence and move on | Apologise, or hide the limit |
| Second person for instructions ("run `quirq demo`") | "Simply", "just", "easily" and other trivializers |

Mechanics:

- American English, sentence case for headings and titles, Oxford comma.
- Spell numbers as digits with units (`88 to 96 percent` in prose, `88–96%` in
  figures and captions).
- Headlines: one idea, compact enough to read at display size. On pages built
  on the site's story beats, write exactly two headline lines rather than
  relying on wrapping.
- A lede never repeats the title. A caption qualifies evidence; it never
  carries the main claim.
- Calls to action: one primary, at most one secondary.

## 3. Naming

### The brand

- **quirq** is lowercase mid-sentence, in titles and headings, and in the
  wordmark: "Intro to quirq", "quirq · work at light speed". The site
  capitalises it only where a sentence begins ("Quirqs are never
  self-reported") and in the metric name **Quirq Efficiency Ratio (QER)**.
  Never write QUIRQ.
- The unit is **a quirq**, plural **quirqs**. Tokens meter what agents consume;
  quirqs meter what they deliver. Do not use quirq as a verb.
- Tagline as shipped on the site: "work at light speed".
- The separator in titles and lockups is a middle dot with spaces: `quirq · work at light speed`.
- Product and command names appear in code formatting when they are literal:
  `quirq begin`, `quirq settle`, `.quirq/ledger.jsonl`.

### Files and slugs

- Lowercase kebab-case, ASCII only, at most 64 characters.
- The file or folder name and the `slug` field match exactly.
- Slugs describe the content, not its position or date: `the-orientation-tax`,
  not `post-3` or `2026-08-final-v2`.
- Variants are suffixes, in this order: `<slug>[-<role>][-<theme>][@<scale>].<ext>`
  - role: `card`, `og`, `hero`, `fig-<n>`, `thumb`
  - theme: `light` or `dark`, only when the asset differs by theme
  - scale: `@2x` only for raster exports that need it
  - e.g. `the-orientation-tax-fig-1-dark.svg`, `the-orientation-tax-og.jpg`
- Never reuse a slug for different content. A retired slug stays retired.

## 4. Images and figures

### Sizes and formats

| Use | Size (px) | Ratio | Format | Weight budget |
|---|---|---|---|---|
| Post card art | 900 × 504 | 16:9 | JPG (q≈80) or WebP | ≤ 120 KB |
| Social / OG card | 1200 × 630 | 1.91:1 | JPG | ≤ 200 KB |
| Partner / logo tile | 680 × 357 | 1.91:1 | JPG or SVG | ≤ 80 KB |
| Hero / banner | 2000 wide, any height | as designed | JPG or PNG | ≤ 400 KB _(proposed)_ |
| Figure, chart, diagram | vector | as designed | SVG (or HTML/CSS for data) | ≤ 100 KB |
| Logo, mark | vector | — | SVG | — |

Card and partner sizes match the art currently shipped under
`public/assets/writing/` on the site. Raster masters (full-resolution source
files) live in the library; exported sizes are generated from them, never
upscaled.

### Light and dark rendering

The site is dark (void `#000000`, ink `#f4f3f0`), but library assets get reused
in READMEs, docs, decks and social posts where the background may be white.
So:

- Every figure and diagram renders correctly on **both** `#000000` and
  `#ffffff`. Check both before shipping.
- Prefer one SVG that adapts: transparent background, strokes and text in
  `currentColor` or with a `prefers-color-scheme` style block.
- When one file cannot work on both, ship a `-light` and a `-dark` variant and
  use `<picture>` with `media="(prefers-color-scheme: dark)"`, or GitHub's
  `#gh-dark-mode-only` / `#gh-light-mode-only` fragments in Markdown.
- Never bake a solid background into a figure unless it is part of the art.
  Photographic card art is exempt; check it still reads against the page
  around it.
- Text over imagery keeps its scrim. Check contrast against the brightest part
  of the image, not the average.

### Colour

- Use the brand tokens; do not introduce new hues. Spectrum: red `#ff453a`,
  orange `#ff9f0a`, yellow `#ffd60a`, green `#30d158`, cyan `#2fd2ff`, blue
  `#0a84ff`, purple `#bf5af2`. Neutrals: ink `#f4f3f0`, dim `#a3a39e`, faint
  `#85857f`.
- **Colour is value.** A series measuring delivered outcome takes the
  spectrum. Anything counting consumption (tokens, calls, files, minutes) stays
  monochrome. When the unit does not say, use monochrome.

### Figures

Hand-drawn figures (diagrams and charts drawn as SVG or HTML rather than
exported from a plotting tool) follow these rules:

- **Checked at two widths: 1400 px and 820 px.** 1400 is the wide desktop
  reading width; 820 is the site's narrow breakpoint. At both, every label is
  legible, nothing overlaps or clips, and nothing scrolls horizontally.
- Labels are real text, not outlined paths, so they stay selectable,
  translatable and readable by screen readers.
- Percentages scale to 100, not to the tallest bar present.
- Zero draws nothing. A minimum-width sliver where the source measured zero is
  a false reading.
- Every number in the figure appears in the source, in the same units.
- Every figure carries a text summary with the same values the visual shows
  (a caption, a table, or a visually hidden summary on the web).

### Alt text

- Every `<img>` has an `alt` attribute.
- **Informative images** (figures, screenshots, diagrams): alt says what the
  image shows and the takeaway, in one or two sentences, under ~150
  characters. For a chart, name what is compared and the result; the full
  numbers go in the summary, not the alt.
  - Good: "Bar chart: richer project context did not lower token cost across 84 runs."
  - Bad: "chart", "figure 1", "image of graph".
- **Decorative images** (card art that repeats the title beside it): `alt=""`,
  so screen readers skip them. Record that choice in the index (`"alt": ""`
  with `"decorative": true`) so it is deliberate, not missing.
- Never start with "Image of" or "Picture of". Do not repeat the caption word
  for word.
- Markdown images use the same text: `![alt text](path)`.

## 5. Library layout

```text
marketing/
├── docs/
│   └── content-guidelines.md   this file
├── posts/
│   ├── posts.json               index of every post (see below)
│   └── <slug>/
│       ├── index.html           self-contained page
│       └── figures/             figures used only by this post
├── media/
│   ├── media.json               index of every reusable asset
│   ├── images/<slug>/           card, og, hero exports + master
│   ├── figures/<slug>/          reusable figures, light/dark variants
│   ├── video/<slug>/            video + poster frame + captions (.vtt)
│   └── brand/                   logo, mark, favicon, palette, type
└── copy/
    └── <slug>.md                reusable campaign and launch copy
```

### Self-contained pages

A post's `index.html` opens and renders correctly straight from disk: styles
inline, figures inline as SVG or referenced by relative path inside the post
folder, no build step, no network fetch required to read it. Fonts may load
from a CDN but the page must stay readable if they do not.

### `posts/posts.json`

One entry per post, newest first. This file is the single source for card
metadata; pages and listings read from it.

```json
[
  {
    "slug": "the-orientation-tax",
    "title": "The orientation tax",
    "desc": "One or two sentences that are not a copy of the title.",
    "date": "2026-08-01",
    "read": "4 min",
    "category": "thoughts",
    "source": { "title": "How the Environment Affects Agent Performance and Token Cost", "href": "…" },
    "card": "media/images/the-orientation-tax/the-orientation-tax-card.jpg",
    "og": "media/images/the-orientation-tax/the-orientation-tax-og.jpg",
    "status": "published"
  }
]
```

- `slug` matches the folder name. `date` is ISO `YYYY-MM-DD`.
- `category` is one of `announcements`, `thoughts`, `partners`, `guides`
  _(proposed; matches the site's Writings tabs plus guides)_.
- `source` is required when the post reports any finding.
- `status` is `draft`, `published` or `retired`. Retired posts keep their entry.

### `media/media.json`

One entry per reusable asset.

```json
[
  {
    "id": "the-orientation-tax-fig-1",
    "path": "media/figures/the-orientation-tax/the-orientation-tax-fig-1.svg",
    "kind": "figure",
    "alt": "Bar chart: richer project context did not lower token cost across 84 runs.",
    "decorative": false,
    "themes": ["light", "dark"],
    "source": "…note or dataset this figure is drawn from…",
    "license": "quirq",
    "used_in": ["posts/the-orientation-tax"],
    "added": "2026-10-06"
  }
]
```

- `kind`: `image`, `figure`, `video`, `brand`.
- `license`: `quirq` for our own work; otherwise the licence and attribution
  for third-party material. No asset ships without one.
- `used_in` lets the weekly check find every page an asset change touches.

## 6. Validation checklist

Every new or changed piece passes all of these before it merges. Copy the list
into the PR description and tick it.

**Claims and copy**

- [ ] Every number, quote and result names its source, and the source says it.
- [ ] No invented metrics, customers, logos, integrations or testimonials.
- [ ] Results that a later study overturned are flagged as such.
- [ ] "quirq" is lowercase except at a sentence start or in "Quirq Efficiency Ratio"; plural is "quirqs".
- [ ] Headline is one idea; lede does not repeat the title; captions only qualify.
- [ ] Sentence case, American English, Oxford comma; no "simply"/"just"/"easily".
- [ ] Every link resolves; external links that open a new tab say so.

**Files and index**

- [ ] File and folder names are lowercase kebab-case, ≤ 64 characters, and match `slug`.
- [ ] The piece has its entry in `posts/posts.json` or `media/media.json`, with all required fields.
- [ ] Metadata (title, date, reading time) exists only in the index, not duplicated in the page.
- [ ] Post `index.html` opens from disk with no build step and no broken references.
- [ ] Every asset has a licence; third-party assets carry attribution.

**Images and figures**

- [ ] Exports match the size and weight budget table; nothing upscaled.
- [ ] Figures checked at 1400 px and 820 px: no overlap, clipping or horizontal scroll.
- [ ] Figures checked on `#000000` and `#ffffff` backgrounds (or ship `-light`/`-dark` variants).
- [ ] Only brand colours; spectrum only for delivered-outcome values.
- [ ] Percentages scale to 100; zeros draw nothing; every plotted number is in the source.
- [ ] Figure labels are real text, and a text summary carries the same values.
- [ ] Every image has alt text, or `alt=""` recorded as decorative in the index.
- [ ] Text over images keeps contrast at its brightest point.

**Video** _(proposed)_

- [ ] Captions file (`.vtt`) present and checked; poster frame exported.
- [ ] No audio-only information that is not also in captions.

## 7. Sources for these rules

- `quirq-ai/quirq_ai` `AGENTS.md`: content-generation rules, figure rules
  (colour is value, percentages to 100, zero draws nothing, numbers in the
  DOM), accessibility rules, kebab-case slugs of at most 64 characters.
- `quirq-ai/quirq_ai` `app/writing/`: card metadata held once in `data.ts`,
  essays that "may frame, compress and argue, but … may not carry a figure the
  note does not", card art sizes under `public/assets/writing/`.
- `quirq-ai/quirq_ai` `app/globals.css`: brand colour tokens.
- `quirq-ai/quirq_ai` `components/stage/choreo-tree.ts`: the 820 px breakpoint.
- The writings workflow (self-contained pages, a `posts.json` index,
  hand-drawn figures checked at 1400 px and 820 px), as described in the brief
  for this doc. That repository was not reachable from here, so its exact
  schema was not copied; `posts.json` above is a proposal to reconcile with it.
