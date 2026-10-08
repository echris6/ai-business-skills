---
name: research
description: Find out what people want before building or selling anything, by scraping what they already say in public. Use when the user wants a business idea, wants to validate a niche or product, needs audience or competitor research, wants to know what customers complain about or already pay for, or asks to scrape Reddit, Facebook groups, YouTube comments, TikTok, Instagram, Quora, reviews or ad libraries. Names the exact Apify scrapers and settings to use, the search terms to run, how to sort and count what comes back, and how to score niches. Writes everything to business/research.md, which the icp, context, offer, writing, design, marketing and sales skills all read.
---

# Research

People post their problems, questions and purchases in public every day, in their own words. This skill collects that at scale, sorts it, and writes it into one file the rest of the business is built from.

The rule everything else serves: **nothing in the research file is a guess.** Every claim links to a real post, comment, review or ad, and anything inferred is marked as inferred.

## Where this skill sits

This is the first of eight skills that work as a chain. The first three write files into a `business/` folder and the other five read those files before doing anything:

- `business/research.md`: raw findings (this skill)
- `business/icp.md`: the customer profile (icp skill)
- `business/context.md`: the business itself, its tone and what has worked (context skill)

## The two starting points

Work out which one the user is in before scraping anything.

**No idea yet.** The goal is a niche with urgency. There are two routes, and the first is better when it works:

1. Pull it out of the user's own experience. Ask about their jobs, hobbies, things they've fixed for themselves and things people ask them for help with, and keep asking until a niche they know deeply shows up. Niche knowledge is mechanical, not motivational: spotting which questions signal money, writing answers that read as expert and handling the sales conversations all depend on it. An average niche known deeply beats a great niche known from outside.
2. Start from the market. List 10 to 15 candidate niches where people are in a hurry or already spending money, scrape the last three months of each, score them (see scoring below) and let the user pick from the top of the table.

**Has a product or an idea.** Skip the niche hunt. Go straight to where the buyers are and collect what they say about the problem, the current solutions and the price.

## What you are looking for

A market worth entering shows three things at once:

- **Repetition:** many different people with the same problem.
- **Money:** they already pay for something that solves it badly, such as books, courses, tools or services.
- **A gap:** the paid solutions get the same specific complaints again and again.

"People complain about X" is a weak signal. "People pay $40 for a worse answer to X" is a strong one.

## Setting up the scrapers

Most of the collection runs on Apify, which hosts ready-made scrapers and charges per result. At the time of writing the scrapers below cost roughly $1.50 to $5 per 1,000 items, so a full sweep of a niche costs a few dollars. The user needs an Apify account and an API token, and the agent runs the scrapers through the Apify MCP server, the API or the Apify CLI.

Scraper names change over time. If one below is missing, search the Apify Store for the platform name and pick the most-used result.

| Source | Apify scraper | Main settings |
| --- | --- | --- |
| Reddit | `trudax/reddit-scraper-lite` | `startUrls` (subreddit or thread URLs) or `searches`, `sort`, `time`, `maxItems` |
| Facebook groups (public) | `apify/facebook-groups-scraper` | `startUrls` (group URLs), `resultsLimit`, `onlyPostsNewerThan` |
| YouTube videos | `streamers/youtube-scraper` | `startUrls` (channel URLs) or `searchQueries`, `maxResults`, `sortingOrder` |
| YouTube comments | `streamers/youtube-comments-scraper` | `startUrls` (video URLs), `maxComments` |
| TikTok | `clockworks/tiktok-scraper` | `hashtags` or `searchQueries`, `resultsPerPage` |
| TikTok comments | `clockworks/tiktok-comments-scraper` | `postURLs`, `commentsPerPost` |
| Instagram | `apify/instagram-hashtag-scraper`, `apify/instagram-comment-scraper` | `hashtags`, `resultsLimit` / `directUrls` |
| Google Maps reviews | `compass/crawler-google-places`, `compass/Google-Maps-Reviews-Scraper` | `searchStringsArray`, `locationQuery`, `maxCrawledPlacesPerSearch` / `startUrls`, `maxReviews` |
| Meta Ad Library | `apify/facebook-ads-scraper` | `startUrls` (an Ad Library search URL), `resultsLimit`, `activeStatus` |
| Amazon reviews | `junglee/amazon-reviews-scraper` | `productUrls`, `maxReviews`, `filterByRatings` |
| Trustpilot | `automation-lab/trustpilot` | `companyUrls`, `maxReviewsPerCompany`, `stars` |

Always set the result limit. A scraper with no limit will keep going and keep charging.

## Source by source

Pick sources by where the audience spends time. Younger audiences are on TikTok and Instagram, older ones are on Facebook, and some niches live on YouTube or Reddit and nowhere else.

### Reddit

The richest source for most niches.

- **Free route:** Reddit's public RSS works with no API key. Add `.rss` to any subreddit or thread URL to get posts and comments with username, text, title, permalink and timestamp. Keep it to roughly one request per minute per IP. This is enough for daily monitoring.
- **Volume route:** the Apify scraper, for the top posts of the last year and everything from the last three months.
- **Finding the subreddits:** search Reddit for the niche's main term, the problem in plain words, and the names of competing products. Keep the ones where the audience complains, asks and celebrates. Skip the ones where sellers talk to each other.
- **Searches to run inside each subreddit:** "how do I", "is there a", "recommend", "worth it", "alternative to", "I'd pay", "tired of", "anyone else", plus each competitor's name.
- **What to flag:** the same question asked every month by different people, threads where a long answer got thanked heavily (the answer has value), anyone saying "I'd pay for", "is there a course on" or "someone should make", and complaints about existing products.

### Facebook groups

Where several audiences live almost entirely: local trades, hobbies with older members, parenting and many consumer niches.

- **Public groups:** the Apify scraper reads them without a login. Pull the last three months.
- **Private groups:** join the three to five biggest and read a few weeks of posts by hand. Never run a scraper through the user's own logged-in Facebook account, because that puts the account at risk.
- **What to flag:** questions that come back every week and posts whose answers get hundreds of comments.

### YouTube

- Pull the last 50 to 100 videos from 10 to 20 channels in the niche: the big ones, the fast-growing small ones and adjacent niches with the same viewer.
- Work out each channel's median views and flag every video that did 3x its channel's median or more. Those outliers are proven demand, because they beat their own channel's baseline. A small channel with one huge video says more than a huge channel with an average one.
- Scrape the comments on the outliers. Recurring questions are things people still want answered, "part 2 on X please" across several channels is a validated topic nobody has made, and the wording people use is title language.
- Type the niche's main term into YouTube search and collect the autocomplete suggestions. Add each letter of the alphabet after the term to get more.

### TikTok and Instagram

- Scrape the top posts for the niche's hashtags and search terms, then the comments on the 20 to 30 best performers.
- For each top post record the hook, the on-screen text, the format and the length. Recurring hooks and formats are what the niche has already proven.
- When the content is video, give the agent an API key for a model that can watch video (Gemini works) so it can read what was said and shown.

### Quora and forums

Questions there are explicit demand statements, and the numbers are public. A question with thousands of followers and no good answer is a product topic. Search the Apify Store for a Quora scraper, or collect the top 30 questions for the niche by hand. Niche forums and Discord servers that are open to the public work the same way.

### Reviews

- **Amazon books and products in the niche:** five-star reviews show the result people wanted, and three-star reviews list what the product failed to deliver, in the buyer's words. "I wished it covered X" across several products is a product spec the market wrote for you.
- **Trustpilot, G2, app stores and Google Maps:** the same reading for software and services.
- **Course marketplaces** (Udemy, Skillshare, Gumroad, Whop): what sells proves the category, and the reviews on the bestsellers show the gaps. A crowded shelf is a good sign, because competition is proof of spending.
- Note sentences that start with "I finally", "I was tired of" and "I didn't expect". They are ready-made copy.

### Ad libraries

The Meta Ad Library and TikTok Creative Center are free and public. Search for the niche's terms and competitors' names. An ad that has been running for months is usually one that pays for itself, so record its first line, its offer, its format and how long it has run.

### Search data

Google autocomplete and "People also ask" for the niche's main terms show what is searched for word by word. Google Trends shows whether interest is growing or fading. Search demand matters twice for any business that will sell through content, since posts that rank keep selling for years.

## How much to pull

For every item keep the text, the engagement (upvotes, likes, replies), the date and the permalink. Aim for a few hundred posts and comments per niche before drawing any conclusion. Ten posts is an anecdote.

Only collect public content. Don't scrape anything behind a login the user has no right to use, and don't keep personal details beyond a public username.

## Sorting

Save the raw results as files (JSON or CSV) and work on them with code, so counts are real counts. Then put every item into one of five piles:

- **Complaints:** the problem, in their words.
- **Questions:** what they keep asking.
- **Purchases:** what they bought, what it cost and whether it worked.
- **Workarounds:** what they do by hand or built for themselves because nothing fits.
- **Language:** exact phrases that repeat across different people.

Group items that say the same thing, count each group, and keep the two or three best quotes per group with their links. A complaint from one person is noise and the same complaint from forty people is a market.

Tag urgency wherever it shows: a deadline, money being lost, "I've tried everything", someone asking for a recommendation, or someone paying for a solution they say is bad.

Tag each quote with the stage it belongs to: aware of the problem, comparing solutions, objecting to a solution, or talking after a purchase. The writing skill uses these tags to pick which words go where.

An entry in the file looks like this (a made-up example to show the format):

```
3. Clients cancel at the last minute and the slot goes unpaid (41 mentions, 12 urgent)
   - "third no-show this week, that's $180 I'm never getting back" [link] (problem)
   - "I started taking deposits and half my regulars got offended" [link] (objection)
   Already paying for: booking apps at $30 to $60 a month, most say reminders don't stop it
```

## Scoring niches

When the user is choosing between niches, put them in one table:

| Niche | Sources | Items scanned | Urgency count | Already paying for | Top complaint about what they pay for | Where to reach them |
| --- | --- | --- | --- | --- | --- | --- |

Rank by urgency count first and by "already paying" second. People who already pay for a bad solution are easier to sell to than people who have never paid for anything. Show the table and let the user pick. Don't pick for them.

## Competitors

For each product already sold to this audience, record:

- What it is and its format (course, tool, service, community).
- The price and how it is charged.
- The promise in its headline.
- Where its customers come from (ads, a creator's audience, search, a marketplace).
- The three complaints that repeat most in its reviews.
- Its longest-running ads.

The gap to look for is a complaint that repeats across several competitors and that none of them answers. Before the user commits, check that their planned product can answer the top three complaints about the two closest competitors. If it can't, the angle isn't sharp enough yet.

## The output file

Write `business/research.md` in this shape:

```
# Research: [niche or product]
Last scrape: [date]. Sources: [list with item counts].

## Summary
[5 to 8 lines: who these people are, what they want most, what they pay for now, the biggest gap.]

## Complaints (ranked by count)
1. [complaint in plain words] ([count], [urgent count])
   - "[exact quote]" [link] ([stage])
   - "[exact quote]" [link] ([stage])

## Questions (ranked by count)
## Purchases and prices
## Workarounds
## Language bank
[exact phrases, grouped by topic, each with a link]

## What already works in content
[outlier videos, top posts and long-running ads: hook, format, link]

## Competitors
[one block per competitor]

## Gaps
[each gap, with the evidence for it]

## Guesses
[anything inferred and not directly shown by the data]
```

Keep the raw scrape files next to it in `business/raw/` so any count can be checked.

## Keeping it fresh

Re-scrape monthly and add a dated section at the top with what changed. New complaints and new outliers show where attention is moving, and a topic whose outliers all fall in the last 60 days is a trend to act on now. For daily monitoring, the Reddit RSS route is free and is enough to catch new buying-intent posts as they appear.

## Common mistakes

- Scraping where sellers talk instead of where buyers talk.
- Drawing conclusions from the loudest thread and not from counts.
- Paraphrasing quotes. The exact words are the value.
- Treating interest as demand when nobody in the data is paying for anything.
- Researching a niche the user knows nothing about because the numbers looked good.

## Running this skill

When the user has no idea: run the two routes, deliver the scored niche table and wait for the user to pick. When the user has a niche or product: confirm the sources, state the expected cost of the scrape, run it, sort, and deliver `business/research.md` with a short summary of the three strongest findings. When the user asks a single question ("what do people hate about X"): answer from the data with quotes and links, and add it to the file.

If the data does not show demand, say so plainly. A niche with no urgency and nobody paying is a finding, and forcing a positive answer here costs the user months later.
