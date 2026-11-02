# Release Notes Guidelines

This directory contains version-specific release notes for **Trevix Explorer**.

---

## 📌 Naming Convention

Each release note file **must** be named using the exact semantic version string from `package.json` without the `v` prefix:

```text
release-notes/
├── 1.0.6.md
├── 1.0.7.md
└── README.md
```

- ✅ Correct: `1.0.7.md`
- ❌ Incorrect: `v1.0.7.md`, `release-1.0.7.md`

---

## 🎯 Usage in Automated CI & In-App Updater

During the automated release workflow (`.github/workflows/release.yml`):

1. The CI pipeline validates that `release-notes/<version>.md` exists for the release tag.
2. The contents of `release-notes/<version>.md` are automatically attached to the GitHub Release in `RaffiDevYT/trevix-explorer-releases`.
3. When users check for updates or receive update notifications inside Trevix Explorer, `UpdateService` fetches and displays these release notes directly in the update dialog.

---

## ✍️ Structure & Style Rules

1. **Language**: Must be written in **English**.
2. **Top Section**: Start with `## Behavior Changes` highlighting important behavioral or breaking updates.
3. **Sections**: Group changes logically into:
   - `## Behavior Changes`
   - `## Security`
   - `## Fixed`
   - `## Added`
   - `## Changed` (if applicable)
4. **No Internal File References / Hashes**: Write user-facing summaries without internal source file paths or commit hashes.
