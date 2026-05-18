---
name: Bio Formatter Guide
slug: bio-formatter-guide
category: Documentation
---

# Bio Formatter Guide 📝

To make sure the system and AI understand who you are without any technical complications, use these simple fields at the top of your file (between the `---` lines). Forget about complex nesting!

## Frontmatter (Flat Metadata)

| Field | Type | Required | Description |
|---|---|---|---|
| `name` | `string` | Yes | Your name or your business name. |
| `language` | `string` | No | (Directory only) ISO Language code. |
| `status` | `enum` | No | Lifecycle of the profile: `draft`, `published`. |
| `visibility`| `enum` | No | Access level: `public` (open to all), `protected` (password required). |
| `password` | `string` | No | Mandatory if `visibility` is `protected`. Key to grant access to the profile. |
| `role` | `string` | No | Your main role or tagline (e.g., "Software Architect"). |
| `location` | `string` | No | Your base location (e.g., "Madrid, ES" or "Remote"). |
| `email` | `string` | No | Your direct email address. |
| `phone` | `string` | No | Your phone number or WhatsApp. |
| `[social network]` | `string` | No | Full URL of your profile. Supported: `website`, `linkedin`, `github`, `x`, `instagram`, `youtube`, `facebook`, `tiktok`. |

*(💡 **Image Magic**: You don't need to declare the image in this table. Simply place a photo named `avatar.jpg`, `profile.png`, or similar inside your `attachments/` folder and the system will automatically use it as your profile picture).*

## Example Frontmatter

```yaml
---
name: Jane Doe
language: en
status: published
visibility: public
role: Software Architect
location: Mexico City, MX
email: jane.doe@example.com
phone: "+52 55 1234 5678"
linkedin: https://linkedin.com/in/janedoe
github: https://github.com/janedoe
---
```
