---
name: Advanced Press Structure & Media
slug: advanced-press-structure
category: Documentation
---

# Leveling Up Your Press 🚀

Ready to add some sparkle? When you want to include local images, videos, or spread your story across multiple pages, it's time to upgrade from a single file to a **Directory Structure**.

## Organizing Your Folder

A Press folder is super easy to organize. It needs an `index.md` as the main page, and you can throw in extra `.md` files for sub-pages. 
*Quick tip: Don't put multiple `.md` files in a folder without an `index.md`, or the system will get confused!*

### The Perfect Setup

```text
my-awesome-press/
├── index.md                (Your main story)
├── behind-the-scenes.md    (A cool sub-page!)
└── attachments/
    ├── cover.png           (We'll automatically use this as your cover image!)
    ├── banner.png
    ├── demo.mp4
    └── cool-report.pdf
```

Just keep your `.md` files right in the main folder, and safely tuck all your pictures and videos inside the `attachments/` folder.

## Adding Media to Your Story 🖼️

Once your frontmatter is set, you can write freely! Sentilis will magically process:

- **Images** (`![My Image](path)`): We love `.png`, `.jpg`, `.jpeg`, `.gif`, `.svg`, and `.webp`.
- **Videos**: We support `.mp4` and `.webm`.
- **Local Links**: Link directly to your sub-pages (we'll make sure they work!).
- **Web Links**: Link out to the wild web (just make sure it's `http` or `https`).

### Your Cover Image (OpenGraph)

Want your post to look stunning when shared on Twitter or LinkedIn? The `image` setting in your frontmatter handles that! If you forget to set it, don't worry—we'll peek into your `attachments/` folder and grab any file named `image.png` (or jpg/webp) for you.

## A Few Golden Rules to Keep Things Smooth 🌟

- **Keep it local:** Make sure every file you link to actually exists inside your folder. No sneaky `../` paths allowed!
- **The Attachments Rule:** Every single image, video, or PDF **must** live inside `./attachments/`. Trying to link something like `./my-photo.png` won't work.
- **Markdown placement:** Keep your `.md` files in the main folder. They don't belong in `attachments/`.
- **Single files keep it simple:** If you're not using a folder, remember you can't use local media.
## Sharing Settings (Inheritance) 👨‍👩‍👧‍👦

When you use a directory with an `index.md` and some sub-pages (like `behind-the-scenes.md`), you don't have to rewrite all your settings!

Your sub-pages will **automatically inherit** the `status` and `visibility` from your main `index.md` file. 

- **Example:** If your `index.md` is set to `status: published` and `visibility: private`, all your sub-pages will also be published and private by default.
- **Want to change it?** No problem! If you want a specific sub-page to have different rules, just add a frontmatter block to that specific file and set its own `status` or `visibility`. Your custom settings will always override the inherited ones!
