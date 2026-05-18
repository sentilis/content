---
name: What is a Bio?
slug: what-is-a-bio
category: Documentation
---

# Welcome to Sentilis Bio! 💼

A **Bio** is a specialized entry in Sentilis designed to showcase a professional resume, portfolio, or a general profile for a professional or a business.

Just like *Press* and *Market*, creating a *Bio* is meant to be extremely easy for any user, allowing everything from a quick single-file profile to a complete multi-language setup with a profile picture.

## How to Create Your First Bio

Depending on your needs, you can create a Bio in two ways:

### 1. The Quick & Simple Way (Single File)
If you just want to publish your profile quickly in one language and don't need to attach a local profile picture, simply create a Markdown file (like `my-profile.md`). 
*Note: Single files are fast, but they do not support local profile pictures or language variants.*

### 2. The Full Experience (Directory)
If you want your profile picture visible and/or want to publish your resume in multiple languages (e.g., English and Spanish), create a **folder** (like `my-profile/`). Inside the folder, create your files naming them with the language code:

```text
my-profile/
├── en.md               (Your profile in English)
├── es.md               (Your profile in Spanish)
└── attachments/
    └── avatar.jpg      (Your profile picture, auto-detected)
```

**Default Behavior:** If an `index.md` file does not exist, the system will automatically pick the first file it finds (e.g., `en.md`) as the default view for your profile. All languages in that folder will share the same picture from `attachments/`.

*Ready to dive deeper? Learn how to tweak your settings in our [Formatter Guide](./bio-formatter.md), or discover how to use the AI-Friendly Harvard Style in our [Advanced Guide](./bio-advanced.md).*
