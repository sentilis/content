---
name: "Press Template: Blog Post / Long-Form Article"
slug: press-template-blog-post
category: Templates
status: published
visibility: public
tags: "press, template, blog, article, long-form"
---

# Press Template — Blog Post 📝

A ready-to-copy **Press** template for a long-form blog post or engineering article. Structure: hook → problem → approach → details → takeaway. Use this for technical deep dives, retrospectives, or opinion pieces.

Copy the block below into a new file (e.g. `migrating-our-monolith.md` or `migrating-our-monolith/index.md`).

```markdown
---
name: "How We Migrated a Monolith to Go Microservices Without Downtime"
slug: "migrating-monolith-to-go"
category: Engineering
status: published
visibility: public
image: ./attachments/image.png
tags: "engineering, migration, go, microservices, postmortem"
authors: "Daniel Okafor"
---

# How We Migrated a Monolith to Go Microservices Without Downtime

Six months ago, our Ruby monolith was processing 600 requests per second at peak — and falling over every Black Friday. Today, the same workload runs across 14 Go services at 8,000 requests per second, with a p99 latency of 120 ms and zero customer-facing downtime during the cutover.

This post is the story of how we got there, what we'd do differently, and the boring engineering choices that mattered most.

## The Problem

Our monolith had three accumulated issues:

1. **Coupled deploys.** Shipping a one-line fix to checkout required rebuilding and redeploying the entire payments stack.
2. **Vertical scaling ceiling.** We were already on the largest available instance type. There was no "bigger box" left to buy.
3. **On-call fatigue.** Every incident pulled in three engineers because nobody fully understood the blast radius of a single bad query.

Rewrites are usually a trap, but the cost of *not* migrating was about to exceed the cost of the migration itself.

## Our Approach: Strangler Fig, Service by Service

We rejected the "big-bang rewrite" from day one. Instead, we used the [Strangler Fig pattern](https://martinfowler.com/bliki/StranglerFigApplication.html): the monolith stayed in production, and we peeled off one bounded context at a time behind a routing layer.

The rough sequence:

1. **Identify a seam.** Find a module with clean inputs and outputs (we started with notifications).
2. **Build the Go service in parallel.** No traffic yet — just unit tests and contract tests against the monolith's interface.
3. **Shadow-traffic it.** Mirror production requests to the new service and diff the responses. Fix bugs until parity is boring.
4. **Cut over with a feature flag.** 1% → 10% → 50% → 100%, with a one-click rollback at each step.
5. **Delete the old code.** This step is non-optional. Two implementations of the same thing is worse than either alone.

## What Made It Work

- **Contract tests as the source of truth.** Every service has a Pact-style contract checked in CI. A breaking change in `service-A` fails the build of `service-B` before it ever ships.
- **One database per service — eventually.** We started with shared-DB-different-tables, then split. Trying to do both at once would have killed us.
- **An on-call rotation that owned the migration.** The team that built the monolith was the same team that dismantled it. No throw-it-over-the-wall.

## What We'd Do Differently

- **Invest in observability first, code second.** We spent two weeks adding OpenTelemetry across the monolith *before* extracting anything. Best decision of the project.
- **Pick boring tech.** Go, Postgres, gRPC, NATS. Nothing we picked appeared on Hacker News that month, and that's the point.
- **Don't migrate the database in the same quarter as the service.** We tried once. We will not try again.

## The Takeaway

Migrations are 10% architecture and 90% discipline. The interesting decisions are the ones you make on Tuesday afternoon — "do we cut over today or wait until the next sprint?" — not the ones in the architecture diagram.

If you're staring at your own monolith wondering whether to break it up, the answer is probably *yes, but slower than you think*. Pick one seam, ship it behind a flag, and earn the next one.

---

*Thanks to Maya, Tobi, and Anouk for reviewing drafts. Mistakes are mine.*
```

> 💡 **Tips:**
> - Use `## Subheadings` liberally — they double as your table of contents and as the SEO outline.
> - Drop charts, diagrams, and screenshots into `attachments/` and reference.
> - For multi-part series, create a directory and add sibling files like `behind-the-scenes.md` next to your `index.md` — they inherit `status` and `visibility`.
