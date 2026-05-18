---
name: Frontmatter (Your Press Settings)
slug: press-formatter-guide
category: Documentation
---

# The Magic Behind the Scenes: Frontmatter ✨

Before you start writing your amazing content, you can tell Sentilis exactly how to handle your Press. We do this by adding a small settings block right at the very top of your Markdown file, tucked between two `---` lines. We lovingly call this the **frontmatter**!

Here is what it looks like:

```yaml
---
name: The Grand Release of Sentilis v2!
slug: sentilis-v2-release
category: Engineering
status: published
visibility: public
image: ./attachments/image.png
tags: "release, v2"
authors: "John Doe, Jane Smith"
---

# Your awesome Markdown content starts right here...
```

## What Can You Customize?

Here are the cool settings you can play with:

| Setting | Type | Do I need it? | Default | What does it do? |
|---------|------|---------------|---------|------------------|
| `name` | `string` | Yes | (we'll guess it) | The catchy title of your Press! |
| `slug` | `string` | Yes | (we'll guess it) | The neat URL link for your post. |
| `category` | `string` | No | `null` | The main topic or theme. |
| `status` | `enum` | No | `published` | Where is it at? `draft`, `published`, or `archived`. |
| `visibility`| `enum` | No | `public` | Who can see it? `public`, `private`, `protected`, or `prime`. |
| `image` | `string` | No | auto-detected | The beautiful cover image for sharing. |
| `tags` | `string` | No | `""` | Helpful keywords to find your post (comma-separated). |
| `authors` | `string` | No | `""` | Give credit to the amazing writers! (comma-separated). |

## Privacy and Publishing 🕵️‍♀️

- **Status:** 
  - `draft`: Still working on your masterpiece.
  - `published`: Live for the world to see!
  - `archived`: Safely tucked away for history.

- **Visibility:** 
  - `public`: Everyone is welcome!
  - `private`: Shh... just for you.
  - `protected`: VIPs only (requires a special link or permission).
  - `prime`: Your absolute best, premium content.
