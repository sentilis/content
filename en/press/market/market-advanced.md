---
name: Product Advanced Guide
slug: product-advanced-guide
category: Documentation
---

# Product Advanced Guide 🚀

Ready to take your products to the next level? Here you will learn about handling assets, auto-detection, and the rules to keep your products shining.

## Folder Structure

When using the directory approach, your setup should look like this:

```text
my-product/
├── product.md
└── attachments/
    ├── image.png           (auto-detected as `image`)
    ├── attachment.zip      (auto-detected as `attachment`)
    └── screenshots/
        └── dashboard.png
```

The `.md` file lives in the root of the directory. Any other referenced file must be inside the `attachments/` folder (subfolders inside `attachments/` are perfectly fine).

### Associated Files

- `image` references the **cover image** of the product (the one that appears in the catalog). It is independent of the images used in the body.
- `attachment` references **a single attached file** (e.g., terms, a spec sheet, or a downloadable package).

Both are uploaded along with the Markdown in the same ZIP bundle.

## Auto-detection

If `image` or `attachment` are not explicitly specified in the frontmatter, the CLI automatically resolves them by convention from the contents of `./attachments/`:

- **`image`**: The first file matching `attachments/image.{png,jpg,jpeg,webp}` (in that priority order). If none exists, the field remains `null`.
- **`attachment`**: The first file matching `attachments/attachment.zip`. If none exists, the field remains `null`.

If the frontmatter explicitly defines the field, auto-detection is skipped and the provided path is validated. If there are multiple matching files (e.g., both `image.png` and `image.jpg` exist), the CLI will throw an error asking you to explicitly pick one via the frontmatter.

## Validation Rules

To ensure everything runs smoothly, keep these rules in mind:

- All referenced files (`image`, `attachment`, body images, and videos) must exist and be inside the root directory (no `..` or escape paths allowed).
- **Every local asset (image, video, zip, pdf, etc.) must be inside `./attachments/`.** References like `./cover.png` or `./media/clip.mp4` in the root will fail; they must be `./attachments/cover.png` or `./attachments/media/clip.mp4`.
- The `.md` file lives in the root of the directory, **never** inside `attachments/`.
- In "single file" mode, references to local assets are not allowed (since there is no `attachments/` folder).
- Remote URLs must use `http(s)://`.
- Web links should not point directly to multimedia files.
- `pressUrl`, if provided, must be an absolute `http(s)://` URL.
- If `price` > 0, `currency` is mandatory.
- `price` must be a number ≥ 0.
- If `kind` is `digital`, `attachment` is mandatory.
- Local links to other `.md` files are not allowed (products are independent entries and do not have children).

## Complete Example

```markdown
---
name: "Pro UI Kit"
slug: "pro-ui-kit"
kind: digital
category: "Design Resources"
status: published
visibility: public
price: 19.99
currency: USD
image: ./attachments/image.png
attachment: ./attachments/attachment.zip
pressUrl: "https://sentilis.me/demo/press/sentilis-v2-launch"
---

# Pro UI Kit

A comprehensive UI kit for your next big project. Includes hundreds of components, icons, and templates.

## What's Included

- 500+ UI Components.
- 200+ Custom Icons.
- Lifetime updates.



You can read the full announcement in the [launch press release](https://sentilis.me/demo/press/sentilis-v2-launch).
```
