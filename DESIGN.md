# Design

## Theme

Dark editorial base. Near-black background fields carry the brand's authority. Off-white and light-grey text. Color appears as punctuation — not wallpaper. Each major project section gets its own color world (purple, green, teal, amber) but these are set-pieces, not the base register. The base is dark and deliberately weighted.

Physical-scene test: A serial entrepreneur and academic explains his work to 200 students who have ten minutes to decide whether to trust him. The ambient context: a lecture hall, a LinkedIn scroll, a phone at a coffee break. The design should feel like the cover story, not the press release.

## Typography

**Display**: Barlow Condensed · weights 700, 800, 900
**Body**: Barlow · weights 400, 500, 600
Source: Google Fonts

*Font selection rationale:* Brand voice is "Credible · Bold · Human." The physical-object test landed on "a conference programme from a serious European event, printed in two weights, no fuss." Barlow Condensed's bold/black compression reads as authority; Barlow's humanist proportions read as approachable. Not on the reflex-reject list. Not editorial-typographic (no display serif, no drop caps). A single family used with committed weight contrast.

### Scale

```
--text-xs:   0.6875rem  / 11px
--text-sm:   0.8125rem  / 13px  
--text-base: 0.9375rem  / 15px
--text-md:   1.0625rem  / 17px
--text-lg:   1.25rem    / 20px
--text-xl:   clamp(1.5rem, 2.5vw, 2rem)
--text-2xl:  clamp(2rem, 4vw, 3rem)
--text-3xl:  clamp(2.5rem, 5.5vw, 4.5rem)
--text-disp: clamp(3rem, 8vw, 7rem)
```

Body max line-length: 68ch.

## Color (OKLCH)

```
--ink:       oklch(14% 0.018 258)    /* near-black, blue-tinted     */
--ink-2:     oklch(28% 0.022 258)    /* dark surface                */
--ink-3:     oklch(40% 0.018 258)    /* medium surface              */
--paper:     oklch(97% 0.006 80)     /* off-white, barely warm      */
--paper-2:   oklch(93% 0.008 255)    /* subtle blue-white           */
--muted:     oklch(58% 0.012 258)    /* muted text                  */
--border:    oklch(88% 0.008 258)    /* light border                */
--border-dk: oklch(24% 0.015 258)    /* dark-bg border              */

/* Accent colors (section set-pieces) */
--blue:      oklch(52% 0.22 258)     /* #1a56db equivalent          */
--purple:    oklch(43% 0.24 298)     /* Skills-UP purple            */
--green:     oklch(48% 0.14 148)     /* Sustainista green           */
--teal:      oklch(57% 0.15 218)     /* L2BGreen teal               */
--amber:     oklch(72% 0.16 68)      /* PM amber                    */
--gold:      oklch(82% 0.14 78)      /* award gold                  */
```

Color strategy: **Committed on section set-pieces; Restrained on the base**. The base (body, cards, layout) uses ink/paper. Project sections commit fully to their brand color.

## Components

### Hero
Left-aligned two-column layout on desktop (text left, photo right). No centered stack. Display headline in Barlow Condensed Black. Single CTA.

### Section headings
No repeated `.sl` labels before every heading. That pattern is AI scaffolding. Section kickers are used *selectively* — on 3-4 key moments, not 15. Where used, they appear as a colored text label (no line decoration, no tracking-heavy uppercase).

### Stats / numbers
Never the "hero-metric template" (big number + small label + background + gradient card). Instead: inline prose callouts, or a bold typographic aside, or integrated into narrative. If displayed as a group, use an asymmetric strip, not a symmetrical 4-column grid.

### Cards
Used only where genuine content isolation is needed (project items, publications). No icon-above-heading template cards. No rounded-corner icon boxes. If categorization is needed, use a leading number, a colored text label, or nothing.

### Card hover
`transform: translateY(-2px)` + `box-shadow` only. No border-color changes on hover (over-designed for this register).

### Award cards
Replace the 9 identical icon-title-description award cards with an editorial timeline-style list. Year left, title right, minimal dividers.

### Teaching institutions
Replace the 9 identical uni-card template with a simple comma-separated running text block or a compact left-aligned list. Identical card grids for lists are the wrong affordance.

## Imagery

The page has real photography. The award section hero image (top3-bildungsmillion.jpg) is the editorial anchor. Stefan's portrait (stefan-bauer.jpeg) in the hero. Hackathon photos in the hackathon section. Use them large. Don't pad with decorative illustrations or icon sets.

## Motion

Page-load: award overlay text stagger (already implemented). Hover transitions: 180ms ease-out on transform only. No entrance animations on cards below the fold — too much, wrong register. `@media (prefers-reduced-motion: reduce)` disables all transforms.
