---
name: "Press Template: Changelog / Quick Note"
slug: press-template-changelog
category: Templates
status: published
visibility: public
tags: "press, template, changelog, release-notes, note"
---

# Press Template — Changelog / Quick Note 🗒️

A ready-to-copy **Press** template for a short, scannable update — product changelog entry, release notes, weekly digest, or a quick "what's new" note. Designed to be read in under 60 seconds.

Copy the block below into a new file (e.g. `release-2026-05.md`). A changelog rarely needs the directory structure — a single file is enough.

```markdown
---
name: "Changelog — May 2026"
slug: "changelog-2026-05"
category: Changelog
status: published
visibility: public
tags: "changelog, release-notes, v2.4"
authors: "Product Team"
---

# Changelog — May 2026

A quick recap of what shipped this month. As always, [reply with feedback](mailto:hello@example.com) — half of these came directly from your suggestions.

## ✨ New

- **Bulk import for contacts.** Drop a CSV with up to 50,000 rows; we'll handle dedup and validation. Available on all plans.
- **Saved views.** Filter, sort, and group your inbox once — then save it. Pin up to 10 views per workspace.
- **Slack notifications, v2.** Thread-aware, with per-channel routing rules.

## 🚀 Improved

- Search is now ~4× faster on workspaces with more than 100k records.
- The mobile app no longer logs you out after 7 days of inactivity (now 30).
- Webhooks retry with exponential backoff instead of a flat 5-minute interval.

## 🐛 Fixed

- Fixed a bug where timezone offsets were dropped on recurring events.
- Resolved a rare crash when uploading attachments larger than 100 MB.
- The "Mark all as read" button now actually marks all as read. Sorry about that.

## 🧹 Deprecated

- The legacy `/v1/contacts.list` endpoint will be removed on **August 1, 2026**. Use `/v2/contacts` instead — [migration guide](https://example.com/docs/migrate-contacts).

---

**Next month:** Calendar sync, custom fields on contacts, and a long-overdue refresh of the analytics dashboard.
```

> 💡 **Tips:**
> - Keep entries under one line each — readers skim changelogs, they don't read them.
> - Use a consistent emoji set (`✨ New`, `🚀 Improved`, `🐛 Fixed`, `🧹 Deprecated`) so returning readers know where to look.
> - Set `status: draft` while writing, then flip to `published` the moment you ship — changelogs lose value if they trail releases by more than a day.
> - No need to set `image` for short notes; OpenGraph falls back to the page title.
