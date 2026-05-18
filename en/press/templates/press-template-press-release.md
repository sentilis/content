---
name: "Press Template: Press Release"
slug: press-template-press-release
category: Templates
status: published
visibility: public
tags: "press, template, press-release, announcement, pr"
---

# Press Template — Press Release 📣

A ready-to-copy **Press** template for an official company announcement — product launches, funding rounds, partnerships, hires, or milestones. Follows the classic journalist-friendly structure: dateline, lede, supporting quotes, boilerplate, and contact.

Copy the block below into a new file (e.g. `series-a-announcement.md` or `series-a-announcement/index.md`).

```markdown
---
name: "Northwind Labs Raises $18M Series A to Scale AI Support for B2B SaaS"
slug: "northwind-series-a"
category: Announcements
status: published
visibility: public
image: ./attachments/image.png
tags: "funding, series-a, ai, customer-support"
authors: "Sarah Chen, Marcus Williams"
---

# Northwind Labs Raises $18M Series A to Scale AI Support for B2B SaaS

**SAN FRANCISCO — March 4, 2026** — Northwind Labs, the AI-native customer support platform, today announced the close of an $18 million Series A round led by Sequoia Capital, with participation from existing investors First Round Capital and Y Combinator. The new funding brings total capital raised to $22.5 million and will accelerate hiring, expand European data residency, and deepen integrations with Zendesk, Intercom, and HubSpot.

Founded in 2024, Northwind helps B2B SaaS companies resolve Tier-1 support tickets autonomously while keeping a human in the loop for sensitive cases. Since launching out of Y Combinator in early 2024, the company has grown to **$8.4M in ARR**, **180+ paying customers**, and **3.2 million tickets resolved** with a 94% customer satisfaction rate.

## Quote — Sarah Chen, Co-Founder & CEO

> "Support has been the most under-invested function in SaaS for two decades. We built Northwind because the best support teams shouldn't need to choose between speed, quality, and cost — they should get all three. This round lets us bring that to ten times as many customers in 2026."

## Quote — Sonya Huang, Partner at Sequoia Capital

> "Northwind is the rare AI company where the metrics speak louder than the demo. The combination of 138% net retention and best-in-class CSAT is what convinced us to lead the round."

## About Northwind Labs

Northwind Labs is the AI-native customer support platform for high-growth B2B SaaS companies. Headquartered in San Francisco with team members across the US and Europe, Northwind is SOC 2 Type II compliant and supports EU/US data residency. Learn more at [northwindlabs.com](https://northwindlabs.com).

## Media Contact

- **Press inquiries:** press@northwindlabs.com
- **Spokesperson availability:** Sarah Chen (CEO), Marcus Williams (CTO)
- **Press kit:** northwindlabs.com/press

###
```

> 💡 **Tips:**
> - The `###` at the end is the traditional press-release "end mark" — keep it; journalists look for it.
> - For embargoed releases, set `status: draft` and `visibility: protected` with a password, then flip to `published` / `public` on the embargo date.
> - Drop your hero image at `attachments/image.png` for auto-detected OpenGraph previews on LinkedIn/X.
