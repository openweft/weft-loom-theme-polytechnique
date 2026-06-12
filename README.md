# weft-loom-theme-polytechnique

`polytechnique` brand theme for weft-loom compile tooling.

**Signature** : PANTONE 7694C ≈ `#01426A` (deep navy) — the official
"bleu X" of the École polytechnique visual identity. The brand is
**blue**, not red ; an earlier draft of this theme used Bordeaux
which has no grounding in the charter.

Sourced from the 2021 *Charte graphique* (École polytechnique press
office) :
- Kit page : https://www.polytechnique.edu/presse/kit-media
- Charter (PDF) : `/sites/default/files/content/pages/documents/2022-02/Charte%20graphique%202021%20%C3%89cole%20polytechnique_compressed.pdf`

## Palette

| Role     | Hex       | Pantone        |
| -------- | --------- | -------------- |
| Primary  | `#01426A` | 7694C          |
| Mid-blue | `#0085CA` | PROCESS BLUE   |
| Cyan     | `#00A9CE` | 312C           |
| Paper    | `#ECE8DC` | WARM GREY 1C   |
| Text     | `#53565A` | COOL GREY 11   |

The full charter palette is 24 colours ; this theme uses a
restrained subset to keep slides readable. PRs welcome to wire in
additional palette entries for chart fills, etc.

## Typography

- Headings : **Roboto Slab** (legacy Droid Serif from the charter's
  digital typography section)
- Body : **Mulish** (formerly Muli — renamed by the Google Fonts
  maintainer in 2019 ; same font)

Both available on Google Fonts and embedded by the slide renderer
automatically.

## Wordmark rules

The charter pins the institution wording strictly :

- `École polytechnique` (lowercase `p`) — primary form
- `Polytechnique` — short form
- `l'X` (lowercase `l`) — informal form

`École Polytechnique` (uppercase P) or `L'X` (uppercase L) are
brand violations and should be corrected when found.

## Usage (Marp slides)

```yaml
---
marp: true
theme: polytechnique
---

# Slide title
```

`section.lead` styling is provided for the title slide :

```markdown
<!-- _class: lead -->

# Title here
## Subtitle here
```

## Distribution

Published as an OCI artifact at
`ghcr.io/openweft/weft-loom-theme-polytechnique:<tag>`. Tool images
consume it via multi-stage `COPY --from=` :

```dockerfile
COPY --from=ghcr.io/openweft/weft-loom-theme-polytechnique:latest /marp/polytechnique.css /opt/marp/themes/polytechnique.css
```

## Brand integrity

The CSS targets the institution's published visual identity. If a
hex drifts due to a re-brand or charter revision, open a PR with
the citation. Institution logos + wordmarks remain the property of
the École polytechnique ; this repo references them only by colour
and typography, never bundled as image assets.

## License

BSD-3-Clause (openweft).

## Cover slide / logo

The theme renders a brand-typography wordmark on `section.lead`
slides ; no institutional logo file is bundled (trademarks remain
the institution's property and aren't redistributable under
BSD-3-Clause).

If you have the right to use the official logotype in your deck,
supply your own image via the `--x-logo` CSS variable :

```markdown
<!-- _class: lead -->
<!-- _style: "--x-logo: url(/path/to/your/logo.svg)" -->

# Title here
## Subtitle here
```

Official logo source : https://www.polytechnique.edu/presse/kit-media (kit logo print / web).
