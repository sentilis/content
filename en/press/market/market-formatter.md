---
name: Product Formatter Guide
slug: product-formatter-guide
category: Documentation
---

# Product Formatter Guide 📝

Every Product begins with a little bit of magic at the top of the file, known as the "frontmatter". This is where you define all the metadata for your product using YAML.

## Frontmatter (YAML Metadata)

At the beginning of your Markdown file, metadata is defined between two `---` lines:

```yaml
---
name: Pro UI Kit
slug: pro-ui-kit
kind: digital
category: Design Resources
status: published
visibility: public
price: 19.99
currency: USD
image: ./attachments/image.png
attachment: ./attachments/attachment.zip
pressUrl: https://sentilis.me/demo/press/sentilis-v2-launch
---

# Markdown Description...
```

### Frontmatter Fields

| Field | Type | Required | Default | Description |
|---|---|---|---|---|
| `name` | `string` | Yes | (inferred) | Readable name of the product. |
| `slug` | `string` | Yes | (inferred) | Unique identifier. |
| `kind` | `enum` | No | `service` | Kind: `service`, `product`, `digital`. |
| `category` | `string \| null` | No | `null` | Category or collection. |
| `status` | `enum` | No | `published` | Lifecycle: `draft`, `published`, `archived`. |
| `visibility` | `enum` | No | `public` | Access: `public`, `private`, `protected`, `prime`. |
| `price` | `number` | No | `0` | Price (>= 0). |
| `currency` | `string \| null` | No | `null` | ISO Currency (USD, EUR...). |
| `image` | `string \| null` | No | auto-detected | Cover image in `attachments/`. |
| `attachment` | `string \| null` | No | auto-detected | Attachment in `attachments/`. |
| `pressUrl` | `string \| null` | No | `null` | Link to an associated Press entry. |
| `description` | `string \| null` | No | (Markdown body) | Short summary. |

### Valid Values

**Status:** `draft`, `published`, `archived`.
**Visibility:** `public`, `private`, `protected`, `prime`.

**Kind:**
- `service`: A service provided by the profile (consulting, mentoring, etc.). Default value.
- `product`: A storable physical product.
- `digital`: A downloadable digital product. **Requires `attachment`** — the file the buyer receives.

Any other value will trigger a validation error.

## Markdown Content

After the frontmatter comes the Markdown body, which is stored in the Product's `description` field. The following are automatically parsed:

- **Images** (`![alt](path)`): Supported formats `.png`, `.jpg`, `.jpeg`, `.gif`, `.svg`, `.webp`.
- **Videos**: Supported formats `.mp4`, `.webm`.
- **External Links**: Must point to `.html` or non-multimedia resources; `#...` anchors are allowed.
