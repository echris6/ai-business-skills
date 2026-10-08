---
name: offer
description: Decide what to sell, price it, prove people will pay, and build it. Use when the user wants to turn research into a product, choose between an info product, a service or software, set a price, tiers or a guarantee, validate or pre-sell an idea before building, or build the product itself, whether that is a PDF guide, a done-for-you service or a web app. Covers the four validation tests that run before anything is built, how to structure and write an info product, how to scope a service, and a proven SaaS stack (Next.js, Vercel, Supabase, Clerk, Railway or Fly.io) with the build order, commands and fixes. Reads business/research.md, business/icp.md and business/context.md and writes business/offer.md.
---

# Offer

A product is what you make. An offer is what the customer is told they get, for what price, with what promise. Most people build first and look for buyers second. This skill runs the order that works: settle the offer, prove people will pay, and only then build the product behind it.

## Where this skill sits

This is the fourth of eight skills that work as a chain. Before doing anything, read `business/research.md` (what the market says), `business/icp.md` (who the customer is) and `business/context.md` (the business and its tone). If they're missing, run those skills first or ask the user for the short version: who is this for, what do they want, and what do they pay for today.

## Step 1: pick the form

There are three forms and each suits a different situation.

**Info product.** Knowledge packaged so someone can buy the shortcut: a guide, a system, a template pack, a course. It is the fastest thing to build, with no stock, no code and no delivery work. It fits when the research shows the same questions asked again and again and the answer can be written down.

**Service.** You (or your agents) do the work for them. It fits when people say they want the result but not the work, and it is the fastest form to get paid for because nothing has to be built in advance.

**Software.** A tool that does the job for many customers. It fits when the same job repeats for every customer and the manual version has already been proven as a service or a method. Building software before the manual method has worked is the most common way to lose months.

When unsure, start with the form that tests demand most cheaply. A service or a short guide can be sold this week, and what customers ask for next shows whether software is worth building. A common path is a free method given away in posts, then a paid guide, then a done-for-you service for the people who ask for it, then software once the service is repeatable.

## Step 2: write the offer

One paragraph that covers:

- **Who** it is for, in the words of the ICP.
- **The outcome** they get, stated the way they describe it in the language bank.
- **What they receive**, concretely: pages, deliverables, features, how long it takes.
- **The price.**
- **The promise**: a guarantee or a clear statement of what happens if it doesn't work.
- **What is not included.**

A vague offer ("improve your marketing") loses to a specific one ("get your first 10 clients from local businesses"). If the offer can't be written in one paragraph a stranger would understand, the product isn't clear yet.

## Step 3: price it

Price from evidence, not from a feeling:

1. What do these people already pay for similar things? (Research file, purchases and competitors.)
2. What is the outcome worth to them in money or time?
3. What does it cost you to deliver each sale?

Rules:

- Set the price inside the range the customer already treats as normal, unless the offer is clearly different from what exists.
- Price on the value of the outcome, not on page count or hours.
- Underpricing reads as low quality in most niches.
- A simple ladder works well: the core product, a higher tier with templates or extras, and later a premium tier with access, updates or done-for-you work.
- The honest test is whether the people who already asked about it would pay this without hesitating. Price is also the easiest thing to test, by changing it.

Ask the user to confirm the final number. Never invent a price or a revenue projection on their behalf.

## Step 4: prove it before building

Build only after at least two of these four signals show up.

1. **The already-pays test.** Evidence of spending on this problem: competing products with visible sales or review counts, services charging for it, tools with pricing pages.
2. **The value-post test.** Publish helpful content on the exact problem where the audience is (a Reddit post that gives real answers away works well) and measure what comes back. Upvotes show interest. DMs and "where can I learn more" replies show intent to buy. If the topic matters, engagement shows up from the first post. This test also builds the reputation the selling phase needs.
3. **The pre-sell.** A one-page description of the product with a buy button or a waitlist, shared in the same places and with the people who messaged. Real payments or real emails are the strongest signal. People who won't give an email for it won't give money for it.
4. **The gap check.** Read the reviews of the two closest competing products and confirm the planned product answers their top three complaints.

Agree the pass mark with the user before running the tests, and write the result into the what-worked log in `business/context.md`.

If the tests fail, the research file already holds the next candidate. Dropping a topic after a day costs nothing, and dropping it after three weeks of building costs the project its momentum.

## Step 5: build it

### Info product

- **The format follows the problem.** A PDF or Notion guide for knowledge and systems, which is fastest to make and easiest to update. Templates, swipe files or spreadsheets when the buyer wants the thing more than the explanation. Video only when the subject is visual, like software walkthroughs or physical technique. Most courses would sell and deliver better as a sharp guide plus a few screen recordings.
- **Version one is the smallest format that fully solves the problem.** For most topics that is a 20 to 30 page guide. A guide that ships this week beats a course that never ships.
- **Structure by outcome, not by topic.** Open with the result and who it is for. Then the steps in the order someone would do them, each specific enough to act on today. If a reader would have to ask "but how exactly do I do X", X isn't finished.
- **Build the outline from the research.** Chapters come from the questions people asked most, and chapter titles use their phrases.
- **Include what goes wrong.** The mistakes and the "what if it doesn't work" paths are what separate a product from a blog post.
- **End with the short path:** "if you only do five things, do these."
- **Draft with AI, check with expertise.** An agent can draft the guide in days, but every claim, number and step is checked against what the user knows first-hand, because people who work in the niche are the audience and one wrong detail costs the product its credibility. The user's own numbers and stories go in, since no competitor can copy them.
- **Give the full method.** A guide that holds back the important part gets refunded.

### Service

- **Write a scope:** what is delivered, by when, what the client has to provide, how many revisions, and what is not included.
- **Package it.** Fixed packages at fixed prices sell faster than custom quotes. A one-time setup plus a monthly fee is a common shape.
- **Break delivery into a checklist** and mark which steps an agent does and which a human approves.
- **Make a sample before selling.** One finished example of the work, ideally made for a real prospect, sells the service better than any description.
- **Write down what "done" means** for each job so the client and the agent agree on it.

### Software

Use one standard stack so no time goes into choosing tools:

- **Next.js + React:** the app, the pages and the API routes.
- **Vercel:** hosting for the app (CLI: `vercel`).
- **Supabase:** Postgres database, file storage and realtime (CLI: `supabase`).
- **Clerk:** sign-up, sign-in and user management (dashboard and env keys, no CLI).
- **Railway or Fly.io:** anything long-running, such as workers, scheduled jobs, scrapers and agents (CLIs: `railway`, `fly`). Railway is the faster start and the default. Fly.io gives more control and multiple regions. Use one per project.

**How the parts divide the work**

- Vercel runs the app, not the long jobs. Serverless functions are for pages, API routes and webhooks, and they have time limits. Anything that scrapes hundreds of pages, processes video, runs an agent loop or polls forever goes to a worker.
- Railway or Fly.io run the work, as a plain Node or Python worker that talks to the same database.
- Supabase is the single source of truth. The app and the workers read and write the same tables. A `jobs` table with a status column handles background work until it clearly can't. Don't add a second database, a queue service or Redis before that.
- Clerk owns identity and Supabase owns data. Rows are keyed by the Clerk user ID, the Clerk session token is passed to the Supabase client, and Row Level Security policies check that ID. Sync a small `users` table from a Clerk webhook.

**Build order.** Check each step works before the next.

```
# 1. Scaffold
npx create-next-app@latest app-name     # App Router, TypeScript, Tailwind
cd app-name && git init && gh repo create

# 2. Auth first (the one dashboard trip)
# Create the Clerk app, copy both keys into .env.local, install @clerk/nextjs,
# wrap the root layout in ClerkProvider, add middleware.ts with clerkMiddleware()

# 3. Database
supabase init
supabase link --project-ref <ref>
supabase migration new initial_schema
supabase db push
supabase gen types typescript --linked > src/lib/database.types.ts

# 4. Wire the app to the data
# One src/lib/supabase.ts factory that passes the Clerk token, used everywhere

# 5. Deploy
vercel link
vercel env add
vercel --prod

# 6. Background work, only when a real long-running job exists
railway init && railway up          # or: fly launch && fly deploy
railway variables set KEY=value     # or: fly secrets set KEY=value

# 7. Webhooks
# Clerk -> user sync. Payment provider -> purchase state. Always verified, always safe to receive twice.
```

**Rules that prevent the usual problems**

- The schema lives in migration files in the repo and is never clicked together in a dashboard.
- RLS is on for every table from the first migration.
- Regenerate the types after every migration.
- The service-role key exists only in the worker's environment, never in the Next.js app and never in the browser.
- Keep a `.env.example` listing every required key.
- Put the database, the workers and the functions in the same region.
- Ship a first version with login and one working page to production on day one, and build everything else on a live app.

**When something breaks**

- Login loops or 401 errors: check the middleware matcher, then whether the Clerk token reaches Supabase, then the RLS policy.
- Works locally and fails when deployed: it is nearly always an environment variable. Run `vercel env ls` and compare with `.env.example`.
- Worker is silent: read `railway logs` or `fly logs` first, then look for rows stuck in `running` in the jobs table.
- Slow pages: move client-side fetching into server components, then add indexes on the columns the page filters by.

For how the app looks, use the design skill.

## Step 6: delivery

Decide what happens in the minute after someone pays, and write it down:

- What they receive and how: a download link, a login or a kickoff message.
- The first message they get and the one thing it asks them to do.
- Where they ask for help and how fast they get an answer.
- The refund rule, stated plainly.

Keep the checkout simple: a payment link from a provider like Whop, Gumroad, Lemon Squeezy or Stripe on a simple page. The product sells or doesn't because of demand and distribution, never because of checkout polish. The sales skill sets the checkout up and tests it.

## The output file

Write `business/offer.md` in this shape:

```
# Offer: [name]
Updated: [date]

## The offer
[the one paragraph]

## Form and why
## Price and how it was set
## Tiers
## Validation
[which tests ran, the pass mark, the result]

## What is built and where it lives
## Delivery steps
## Refund rule
```

Then update the offer section of `business/context.md` so every other skill sees it.

## Common mistakes

- Building before proving. The steps are in this order for a reason.
- Picking a niche from numbers and not from knowledge.
- Making a video course because courses feel more serious, when a guide would ship in a tenth of the time.
- A vague outcome nobody can picture.
- Software before the manual method has been sold even once.
- Invented numbers anywhere in the product or the offer.

## Running this skill

When the user has research but no product: run steps 1 to 4 and stop for their decision before building. When the user already knows what to build: confirm the offer paragraph and the price, then build with step 5. When the user has a product that isn't selling: check the offer paragraph against the ICP's language and objections before touching the product, because the usual problem is the offer. If the tests show nobody wants it, say so and go back to the research file for the next gap.
