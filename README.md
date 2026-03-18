# 🎮 Playtesting

Repository for all playtesting sessions — session notes, tester feedback, screen recordings, bug captures, and milestone reports.

---

## 📁 Folder Structure

```
playtesting/
├── sessions/
│   ├── YYYY-MM-DD-session-name/
│   │   ├── notes.md            # session facilitator notes
│   │   ├── feedback.csv        # structured tester responses
│   │   └── recordings/         # .mp4 / .mov session captures
├── bug-captures/
│   ├── open/                   # screenshots/video of unresolved bugs
│   └── closed/                 # resolved, kept for reference
├── reports/
│   ├── milestone-1/
│   ├── milestone-2/
│   └── final/
├── templates/
│   ├── session-notes-template.md
│   └── feedback-form-template.csv
└── README.md
```

---

## 🌿 Branching Strategy

| Branch | Purpose |
|--------|---------|
| `main` | Finalized, reviewed playtesting records |
| `develop` | Active session uploads and in-progress notes |
| `session/<date-name>` | One branch per playtesting session |
| `report/<milestone>` | Milestone summary reports |
| `fix/<bug-ref>` | Follow-up branch to document a confirmed bug |

**Examples:**
```bash
git checkout -b session/2024-11-01-alpha-group-a
git checkout -b report/milestone-2-summary
git checkout -b fix/bug-042-wall-clipping
```

**Typical session workflow:**
```bash
# Start a session branch
git checkout develop
git checkout -b session/2024-11-15-focus-group

# Add files during/after session
git add sessions/2024-11-15-focus-group/
git commit -m "Session notes and recordings — focus group Nov 15"

# Merge back when reviewed
git checkout develop
git merge session/2024-11-15-focus-group
```

---

## ⚙️ Git LFS

This repo uses **Git LFS** for all video recordings, screenshots, and voxel captures.

```bash
# First-time setup
git lfs install

# Verify tracked types
git lfs track
```

Tracked types: `.mp4` `.mov` `.png` `.vox` `.vxm` `.gif` and more — see `.gitattributes`.

> ⚠️ Raw/uncut recordings go in `recordings/raw/` which is **gitignored**. Only trimmed/relevant clips should be committed.

---

## 🏷️ Tagging

Tag after each milestone's playtesting is complete:

```bash
git tag -a v0.3-playtest-complete -m "Alpha v0.3 playtesting sessions done — 12 testers"
git push origin --tags
```

---

## 📋 Session Naming Convention

Use the format: `YYYY-MM-DD-descriptor`

| Good ✅ | Avoid ❌ |
|---------|---------|
| `2024-11-01-alpha-internal` | `session1` |
| `2024-11-15-focus-group-a` | `new-test` |
| `2025-01-10-milestone2-qa` | `final_final` |

---

## ✅ Post-Session Checklist

- [ ] Notes committed to `sessions/<date>/notes.md`
- [ ] Feedback data exported to `sessions/<date>/feedback.csv`
- [ ] Relevant recordings trimmed and committed (raw files excluded)
- [ ] New bugs added to `bug-captures/open/`
- [ ] Session branch merged into `develop`

---

## 📌 Contacts & Links

- **Project Lead:** _TBD_
- **Related Repos:** [Asset Quality](#) · [Asset Integration](#)
