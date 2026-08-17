# SESAR documentation (Git Sync monorepo)

This repository feeds multiple [GitBook](https://gitbook.com) sections from one repo. Each section has its own **Project directory**, `README.md`, and `SUMMARY.md`.

## Section directories

| GitBook section | Project directory | Landing page |
| --- | --- | --- |
| Get Started | `get-started/` | Welcome to SESAR documentation |
| For Researchers | `for-researchers/` | Create a SESAR account |
| Metadata Schema | `metadata-schema/` | Overview & data model |
| API | `api-reference/` | Overview |
| Vocabularies | `vocabularies/` | About SESAR Vocabularies |

## GitBook setup

In **each** section's Git Sync settings, set **Project directory** to the path in the table above. Do not point multiple sections at the repository root.

After changing project directories, sync once from Git. Avoid editing synced sections in the GitBook UI until each section reads from its own folder — UI exports can overwrite another section's `SUMMARY.md` when directories share a root.

## Editing content

- Edit Markdown in the section folder, then commit and push.
- Regenerate vocabulary list pages (for example `vocabularies/country.md`) from the SESAR API when terms change.
- See [AGENTS.md](AGENTS.md) for GitBook authoring notes.
