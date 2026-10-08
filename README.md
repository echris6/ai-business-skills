# AI business skills

Eight skill files that cover building and selling a product with an AI agent, from finding what people want to closing the sale.

Each skill is a single `SKILL.md` file. Give them to Claude, ChatGPT, Codex or any agent that reads skill files.

## The eight skills

| Skill | What it does |
| --- | --- |
| [research](research/SKILL.md) | Scrapes what people say in public (Reddit, Facebook groups, YouTube, TikTok, Instagram, reviews, ad libraries) and sorts it into one file |
| [icp](icp/SKILL.md) | Turns the research into one specific customer profile |
| [context](context/SKILL.md) | Keeps the business's offer, proof, tone of voice and results in one file |
| [offer](offer/SKILL.md) | Decides what to sell, prices it, tests it and builds it |
| [writing](writing/SKILL.md) | Writes pages, posts, scripts, emails and ads in your tone and the customer's words |
| [design](design/SKILL.md) | Builds the UI from real component libraries and makes ad creatives and thumbnails |
| [marketing](marketing/SKILL.md) | Organic posting, paid ads and outreach |
| [sales](sales/SKILL.md) | Checkout, replies to leads, objections, follow-ups and what happens after the sale |

## How they work together

The first three skills write files into a `business/` folder in your project:

- `business/research.md`
- `business/icp.md`
- `business/context.md`

The other five read those files before doing anything, so everything they produce is based on the same customer, the same offer and the same tone. Start with research and work down the list.

## Installing

Copy each skill's folder into your agent's skills directory (for Claude Code that is `.claude/skills/` in your project or `~/.claude/skills/`), or paste the contents of a `SKILL.md` into the chat and ask the agent to follow it.
