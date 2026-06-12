# weft-loom-theme-polytechnique

`polytechnique` brand theme for weft-loom compile tooling.

**Signature** : École polytechnique (X) — Bordeaux PMS 1955 #B82B36 + black + white.

## Usage (Marp slides)

```yaml
---
marp: true
theme: polytechnique
---

# Slide title
```

The theme is published as an OCI artifact at
`ghcr.io/openweft/weft-loom-theme-polytechnique:<tag>` and consumed by
the tool images via a multi-stage `COPY --from=` :

```dockerfile
COPY --from=ghcr.io/openweft/weft-loom-theme-polytechniqueatest /marp/ /opt/marp/themes/
```

## Layout

| Path                  | Contents                                  |
| --------------------- | ----------------------------------------- |
| `marp/polytechnique.css`   | Marp slide stylesheet                     |
| `pandoc/polytechnique.tex` | pandoc XeLaTeX template (V0.2)            |
| `latex/polytechnique.sty`  | raw LaTeX style package (V0.2)            |

## Brand integrity

The CSS commits to the institution's published visual identity
guide. Re-brand drift → open a PR with the citation. Logos +
wordmarks remain the property of their owners and are referenced
only by colour + typography, never bundled as image assets.

## License

BSD-3-Clause (openweft).
