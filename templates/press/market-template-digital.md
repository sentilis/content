---
name: "Market Template: Digital Product"
slug: market-template-digital
category: Templates
status: published
visibility: public
tags: "market, template, digital, download, ebook, template"
---

# Market Template — Digital Product 💾

A ready-to-copy **Market** template for a digital download — ebooks, design files, code templates, datasets, presets, or any file the buyer receives after purchase.

Remember: when `kind` is `digital`, the `attachment` field is **mandatory** — it's the file the buyer downloads.

Copy the block below into a new file (e.g. `my-download.md` or `my-download/product.md`).

```markdown
---
name: "The Indie Dev Pricing Playbook"
slug: "indie-dev-pricing-playbook"
kind: digital
category: "Ebooks & Guides"
status: published
visibility: public
price: 19.00
currency: USD
image: ./attachments/image.png
attachment: ./attachments/attachment.zip
pressUrl: "https://sentilis.me/demo/press/indie-pricing-launch"
---

# The Indie Dev Pricing Playbook

A 90-page, no-fluff guide to pricing software products as a solo founder or small team. Built from interviews with 40+ profitable indie devs and 3 years of running my own SaaS.

## What's Inside

- **Part 1 — Foundations:** Pricing as positioning, value vs. cost, and why "$X/month" is a strategy, not a number.
- **Part 2 — Frameworks:** Tiering, usage-based billing, lifetime deals, free plans that actually convert.
- **Part 3 — Experiments:** 12 case studies with real numbers (MRR, churn, ARPU before/after).
- **Part 4 — Playbooks:** Step-by-step scripts for raising prices, grandfathering, and migrating plans.

## Format

- **PDF** (90 pages, optimized for screen and print)
- **ePub** (reflowable for e-readers)
- **Spreadsheet** with the pricing-experiment template used in Part 4
- **Bonus:** 6 email scripts for announcing price changes

All files are bundled in a single `.zip` download delivered immediately after purchase.

## Who It's For

- Indie hackers and bootstrapped founders pricing their first or second product.
- Small SaaS teams stuck between $5k and $50k MRR.
- Freelancers transitioning from hourly to productized pricing.

## License

Personal use license. For team or company-wide licenses, write to `licensing@example.com`.

## What Readers Say

> "Raised my prices 40% the week I finished reading it. Zero churn." — Indie founder, 2026

> "Finally a pricing book that respects my time." — SaaS PM
```

> 💡 **Tip:** Put your downloadable bundle at `attachments/attachment.zip` and Sentilis auto-detects it — you can then omit the `attachment` line. The cover image works the same way with `attachments/image.png`.
