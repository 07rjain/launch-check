# Launch Check

A reusable agent skill for checking a software product before launch. It reviews
52 items across nine categories and produces a short, evidence-based report of
what is done, missing, partial, unverified, or not applicable.

## Install

Use the [Skills CLI](https://github.com/vercel-labs/skills), with Node.js 22.20 or
newer:

```sh
npx skills add 07rjain/launch-check
```

Choose the agent you use. Installation is project-level by default. To install
globally for Codex:

```sh
npx skills add 07rjain/launch-check --skill launch-check -a codex -g
```

To preview the available skill without installing:

```sh
npx skills add 07rjain/launch-check --list
```

## Use

Open your product project in your agent and ask:

```text
Use $launch-check to review this product before launch.
Give me a short report of what's done, what's missing,
and what I should fix first.
```

Include the intended launch stage and live URL when available:

```text
Use $launch-check for this project and https://example.com.
We're preparing for a public paid launch.
Keep the report short and prioritize launch blockers.
```

The skill is a set of instructions for your agent. It assesses the project and
any available live environment using the tools and permissions in your session.

## What it checks

| Category | Items |
| --- | ---: |
| Brand and presence | 5 |
| Product experience | 8 |
| Documentation and support | 5 |
| Analytics and operations | 7 |
| Security, privacy, and trust | 6 |
| Payments and monetization | 5 |
| Discovery and distribution | 6 |
| Developer platform | 7 |
| Mobile distribution | 3 |
| **Total** | **52** |

The skill adapts the checklist to the product and launch stage. SDKs, payments,
search tooling, and app-store requirements apply only where relevant.

## Report

The default report is about 250–400 words and includes:

- A readiness verdict and the scope of verification.
- Counts of Done, Partial, Missing, Unverified, and N/A items.
- A compact category table showing completed work and gaps.
- Prioritized next actions with evidence and completion criteria.
- Material checks that could not be verified.

It distinguishes source implementation from verified live behavior and reports
uncertainty explicitly. Fixes and launches require a separate request. The
assessment does not replace a comprehensive security audit or legal review.

## Skill files

- [Instructions](skills/launch-check/SKILL.md)
- [Full checklist](skills/launch-check/references/checklist.md)

## License

[MIT](LICENSE)
