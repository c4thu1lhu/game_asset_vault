# 🖼️ Asset Quality

Repository for tracking, reviewing, and validating game assets before they enter the integration pipeline.

---

## 📁 Folder Structure

```
asset-quality/
├── images/
│   ├── characters/
│   ├── environments/
│   ├── ui/
│   └── vfx/
├── voxel/
│   ├── models/         # .vox / .vxm files
│   └── palettes/
├── video/
│   ├── captures/       # raw gameplay or asset captures
│   └── reference/      # visual reference material
├── reports/
│   ├── qa-checklists/  # .md or .csv QA checklists
│   └── reviews/        # written review notes per asset batch
└── README.md
```

---

## 🌿 Branching Strategy

| Branch | Purpose |
|--------|---------|
| `main` | Stable, reviewed, and signed-off assets only |
| `develop` | Active QA work — push daily here |
| `review/<asset-batch>` | Isolated review for a specific asset group |
| `fix/<issue-name>` | Hotfix for a flagged asset defect |

**Examples:**
```bash
git checkout -b review/character-pack-v2
git checkout -b fix/texture-seam-env-cave
```

---

## ⚙️ Git LFS

This repo uses **Git LFS** for all binary and large files.

```bash
# First-time setup
git lfs install

# Verify tracked types
git lfs track
```

Tracked types: `.png` `.jpg` `.webp` `.vox` `.vxm` `.mp4` `.mov` and more — see `.gitattributes`.

---

## 🏷️ Tagging

Tag milestones after asset batches are approved:

```bash
git tag -a v1.0-character-pack -m "Character pack v1.0 QA approved"
git push origin --tags
```

---

## ✅ QA Checklist (Quick Reference)

- [ ] Resolution matches spec
- [ ] No visible seams or tiling artifacts
- [ ] Naming convention followed (`snake_case`, no spaces)
- [ ] Voxel palette within engine limits
- [ ] Video captured at target frame rate
- [ ] File size within budget

---

## 📌 Contacts & Links

- **Project Lead:** _TBD_
- **Related Repos:** [Asset Integration](#) · [Playtesting](#)
