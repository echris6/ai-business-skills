---
name: context
description: Build and maintain the one file that tells every other skill what this business is, including the product, the offer, the prices, the tone of voice, the proof, the real numbers, the limits and what has worked so far. Use when the user starts a new business or project, wants their agent to remember their brand voice or product details, is tired of re-explaining the business in every chat, wants drafts to sound like them, or wants to log results so the next piece of work starts smarter. Covers the interview that fills the file, extracting tone from real writing samples, the cut list built from the user's edits, and the what-worked log. Writes business/context.md, which the offer, writing, design, marketing and sales skills read first.
---

# Context

An agent that starts every task from zero writes generic work. This skill builds one file that holds everything about the business that doesn't change from task to task, so every other skill starts with the same facts, the same tone and the same record of what worked.

## Where this skill sits

This is the third of eight skills that work as a chain. `business/research.md` holds what the market says, `business/icp.md` holds who the customer is, and `business/context.md` (this skill) holds who the business is. The offer, writing, design, marketing and sales skills read all three before doing anything.

## What goes in the file

**The business in one sentence.** What it sells, to whom, and the result they get.

**The offer.** What the customer gets, the price, the guarantee and what's not included. If the offer skill has written `business/offer.md`, summarise it here in a few lines and point to that file.

**The manual method.** How someone would get the same result by hand, step by step, with the actual tools. This is the raw material for free content. The posts that sell best give the whole manual method away, and the people who don't want to do it by hand become customers.

**Proof.** Real results with real numbers, each with where it came from (a screenshot, a dashboard, a customer message). Customer quotes go here with a note that permission was given. Each number is attached to the thing that produced it, so a result from one channel is never credited to the whole business.

**Honest limits.** What the product does not do and who it is not for. Overclaiming in a post or a DM creates refunds and angry public comments, so the limits are written next to the claims.

**Tone of voice.** The rules for how this business writes (see the next section).

**Look.** The accent color, the fonts and the general style, once the design skill has set them.

**Accounts and links.** The site, the checkout link, the social handles. Never passwords, API keys or tokens. Those stay in the tool that needs them.

**Rules for the agent.** What it must always do and never do. For example: never post without approval, never state a number that isn't in this file, never contact a lead twice in one day.

**What worked.** A dated log of results (see below).

## The interview

When the file doesn't exist, fill it by asking. Ask in small groups and write as you go:

1. What do you sell, and who buys it?
2. What result does the customer get, and how long does it take?
3. What does it cost, and is there a guarantee?
4. How would someone do this by hand without your product?
5. What real results can you show, and where does each number come from?
6. What does it not do? Who should not buy it?
7. What have you already tried to sell it, and what happened?
8. What must I never say or do on your behalf?
9. Can you paste three to five things you wrote yourself and liked?

Pull what you can from the user's site, their past posts and the other two files before asking, so the questions are only about what is missing.

## Building the tone of voice

Tone can't be described with adjectives. "Friendly and professional" describes almost everyone. It has to be extracted from real writing.

1. **Get samples.** Three to five things the user wrote themselves and liked: posts, emails, a page of their site. Writing they did without AI is best.
2. **Find what is consistent.** Sentence length. Whether they use capitals and punctuation normally. The words and connectors they use often. How they open and how they end. Whether they use lists, headers, bold or emoji. Whether they use humor. How they state numbers. How they refer to themselves and to the reader.
3. **Write rules as do and don't.** Each rule gets a short example copied from the samples, so the rule can't be misread.
4. **Keep the samples in the file.** Rules describe the voice and samples are the voice, so drafts are checked against both.

If the user has no samples, interview them. Ask five questions about the business and have them answer by voice or by typing fast, then extract the rules from the answers.

A finished tone section looks like this (a made-up example):

```
### Do
- Short plain sentences joined with "so", "and", "because". ("I tried three apps and none of them stopped it, so I built my own.")
- State numbers exactly and say where they came from. ("41 bookings in March, up from 29.")
- Talk to one person as "you".

### Don't
- No hype words: game-changing, unlock, effortless.
- No questions as openers. ("Tired of no-shows?")
- No emoji, no exclamation marks.

### Cut list
- "Here's the thing" (cut 3 times)
- Closing lines that repeat the point of the paragraph
- Lists of three adjectives
```

**The cut list.** Every time the user edits a draft, compare their version with yours and write down what they removed or changed. Add each habit they cut to the list. After a few rounds this list is the most useful part of the whole file, because it records what this specific person never wants to see again. When the user sends back an edited version, that version is the base for the next draft and nothing they removed comes back.

## Real numbers only

Every figure in the file is the user's actual number. If a number is an estimate, it says estimate next to it. If a number is missing, leave a placeholder like `[revenue from first month]` and ask for it. An invented number in this file ends up in a public post, and one caught lie costs more than the number was ever worth.

If the user gives a number that looks wrong (a price far outside what the research file shows, a result that doesn't add up), ask before writing it down.

## The what-worked log

Marketing only improves when results are written down. After anything is published, sent or launched, add one entry:

```
[date] [channel] [what it was, with link]
Result: [the number that matters for this channel]
Repeat: [what to do again] / Drop: [what not to do again]
```

The number that matters depends on the channel: replies and DMs for a Reddit post, 3-second hold and completion for a short video, click-through and watch time for a YouTube video, cost per sale for an ad, replies for outreach, sales for anything with a checkout link.

Once there are enough entries, keep a short list at the top of the log called **Top three formats**: the three kinds of content or outreach that have performed best. New work leans on those three while still testing new formats on the side.

## The output file

Write `business/context.md` in this shape:

```
# Context: [business name]
Updated: [date]

## The business
## The offer
## The manual method
## Proof
## Honest limits
## Tone of voice
### Do
### Don't
### Cut list
### Samples
## Look
## Accounts and links
## Rules for the agent
## What worked
### Top three formats
### Log
```

## Rules

- One source of truth. When the user says something that contradicts the file, ask which is right and update the file.
- Short enough to read in full every time. If the log gets long, move older entries into an archive section at the bottom and keep the top three formats and the last month visible.
- No secrets in the file, ever.
- Nothing in the file the user hasn't confirmed. Draft sections are marked draft until they do.
- The file describes one business. A second business gets its own folder and its own file.

## When to update it

- The user corrects a fact, a price or a claim: update straight away.
- The user edits a draft: update the cut list before doing anything else.
- A result comes in: add a log entry.
- A customer gives a result or a quote: add it to Proof with the source.
- The offer changes: update the offer section and tell the user which pages and posts still show the old one.

## Running this skill

When the user starts a new business or project: run the interview, pull what you can from `business/research.md`, `business/icp.md` and their site, and deliver `business/context.md` with the gaps listed as questions. When the user wants drafts to sound like them: run the tone steps and show them the rules before using them. When the user reports a result or edits a draft: update the log or the cut list straight away, then carry on with the task. When another skill finds the file missing: build a quick version by asking for the one-sentence business, the offer, the price and two writing samples, and mark it draft.
