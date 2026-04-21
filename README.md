# 🔧 Asset Integration

Repository for tracking the integration of approved assets into the game build — including bundle management, scene wiring, and integration test results.

---

## 📁 Folder Structure

```
asset-integration/
├── bundles/
│   ├── current/        # active .bundle files
│   └── archive/        # retired or versioned bundles
├── voxel/
│   ├── in-engine/      # .vox / .vxm as placed in-engine
│   └── mapping/        # placement or scene mapping notes
├── scenes/
│   ├── test-scenes/    # integration test scenes
│   └── screenshots/    # reference screenshots per scene
├── integration-tests/
│   ├── results/        # .csv or .md test result logs
│   └── checklists/     # per-build integration checklists
├── logs/               # (gitignored) local error logs
└── README.md
```

---

## 🌿 Branching Strategy

| Branch | Purpose |
|--------|---------|
| `main` | Stable, build-ready integration state |
| `develop` | Ongoing integration work |
| `integration/<build-version>` | Per-build integration branch |
| `hotfix/<issue>` | Urgent fix for a broken bundle or scene |
| `test/<scene-name>` | Isolated testing for a specific scene |

**Examples:**
```bash
git checkout -b integration/build-0.4
git checkout -b hotfix/broken-bundle-scene2
git checkout -b test/environment-cave-level3
```

---

## ⚙️ Git LFS

This repo uses **Git LFS** for bundles, voxel files, and captured video.

```bash
# First-time setup
git lfs install

# Verify tracked types
git lfs track
```

Tracked types: `.bundle` `.vox` `.vxm` `.png` `.mp4` and more — see `.gitattributes`.

---

## 🏷️ Tagging

Tag each build integration milestone:

```bash
git tag -a build-0.4-integrated -m "Build 0.4 assets fully integrated and tested"
git push origin --tags
```

---

## ✅ Integration Checklist (Quick Reference)

- [ ] Bundle loads without errors in engine
- [ ] All asset references resolved (no missing links)
- [ ] Voxel models placed at correct coordinates
- [ ] Scene renders at target performance budget
- [ ] Integration test log saved to `integration-tests/results/`
- [ ] No regressions vs. previous build

---

## 📌 Contacts & Links

- **Related Repos:** [Asset Quality](#) · [Playtesting](#)
