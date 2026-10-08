---
name: icp
description: Turn research into one specific customer profile that every piece of marketing gets written for. Use when the user needs an ideal customer profile, a target audience or a buyer persona, wants to know who to sell to, which platform their buyers are on, what words they use or what stops them buying, or when writing and ads feel generic because nobody defined the reader. Covers narrowing an audience to one person, demographics and psychographics, their day hour by hour, how they buy, checking the profile against real people, picking channels, and a filled-in example. Reads business/research.md and writes business/icp.md, which the offer, writing, design, marketing and sales skills read.
---

# ICP

Copy written for everyone gets ignored by everyone. Most marketing fails before a word is written, because it is aimed at a customer who only exists in the founder's head. This skill narrows a broad audience down to one specific person and writes that person down in enough detail that a post, a page or a DM can be written from inside their head.

The bar for a finished profile: you could describe this person's Tuesday from the moment they wake up.

## Where this skill sits

This is the second of eight skills that work as a chain. It reads `business/research.md` and writes `business/icp.md`. If the research file doesn't exist, run the research skill first, or build a quick version from whatever real data the user has (customer emails, reviews, comments, sales calls) and mark the profile as a draft.

## Step 1: narrow it down

Start from the broad audience and keep narrowing until the description is one person.

- "Small business owners" is an audience.
- "Contractors" is a segment.
- "A contractor who runs his own crew, checks his phone between jobs and has never opened a marketing tool" is a customer.

Narrow with the research file. Look at who shows up most in the complaints and purchases, and ask of each slice:

1. Is the problem urgent for them, or only annoying?
2. Do they already spend money on it?
3. Can they decide to buy on their own?
4. Can they be reached in one or two places?

The right slice answers yes to all four. If two slices both pass, pick the one the user knows best.

## Step 2: what drives the purchase

Not every product solves a pain, so name what this buyer is really after. It is usually one of four:

- **A problem** they want gone.
- **A goal** they want to reach faster.
- **Status**, meaning how they want to be seen.
- **Enjoyment**, meaning they want it because they like it.

A game, a hobby product and a tax tool are sold in three different ways. Getting this wrong makes every hook miss, because a hook about pain does nothing for someone who is buying for fun.

## Step 3: write the full profile

**Demographics.** Age range, where they live, their work, income range, family situation and the devices they use.

**Psychographics.** What they care about, what they're afraid of, what they're proud of, who they compare themselves to, who they blame for the problem, what winning looks like to them, and what they believe about the problem that may not be true.

**Their day.** Write it hour by hour. When do they wake up, when are they on their phone, when does the problem show up, when do they have ten minutes and a card in their hand. This decides when and where marketing reaches them.

**What they've tried.** Every solution in the research file's purchases and workarounds, and why each one let them down.

**How they buy.** What they already pay for in this area, what price feels normal to them, whether someone else has to approve it, how long they take to decide, and what makes them trust a seller.

**How aware they are.** Where most of them sit today:

- They feel the problem but haven't looked for a solution.
- They know solutions exist and are comparing them.
- They know this product and need proof and a reason to act.

The same product needs different words for each stage, so the profile says which stage each channel's audience is mostly in.

**Objections.** The reasons they would say no, in their words.

**Language bank.** The exact phrases they use for the problem, the outcome and the existing solutions, copied from the research file with links. These go straight into headlines and hooks. Include their grammar and their level of formality, since copy for contractors sounds different from copy for designers.

## Step 4: check it against real people

A profile written only from text can drift into a customer who doesn't exist. Check it against real faces:

1. Search the product's main term on Instagram.
2. Find an account whose audience matches the profile.
3. Go through its followers and look at actual profiles: their bios, their age, their work, what they post and how they describe themselves.

If the agent has a browser it can do this and report what it saw. The `apify/instagram-profile-scraper` on Apify can also pull public bios for a list of usernames. If neither is available, ask the user to spend fifteen minutes on it and say what they noticed. Then correct the profile. This step often changes the tone and the references in everything written afterwards.

If the business already has customers, they come first. Ten real buyers are better evidence than any amount of scraped text, so read their messages, look at who they are, and ask a few of them one question: "what was going on that made you look for this?" Record the answers word for word.

## Step 5: pick the channels

The channel follows the person. Use the day from step 3 and the sources where they showed up in the research:

- Younger audiences: TikTok and Instagram.
- Older audiences: Facebook.
- Gamers: YouTube and Twitch.
- People looking for an outcome or a method: Reddit and YouTube search.
- Business owners: email, their Google Maps listing and the trade's own Facebook groups.

Name one primary channel and one secondary. Don't pick a platform because it's popular. Pick the one this person already scrolls.

## Step 6: say who it isn't

Write two or three lines on who looks similar but is not the customer: the ones who will never pay, the ones who need something bigger, and the ones who will ask for a refund. This saves time in marketing and in sales conversations.

## The output file

Write `business/icp.md` in this shape:

```
# ICP: [one-line description of the person]
Built from: business/research.md ([date]). Status: [draft / checked against real profiles].

## The person
[5 to 8 lines describing them as one human]

## What drives the purchase
[problem / goal / status / enjoyment, and the specifics]

## Demographics
## Psychographics
## Their day
## What they've tried and why it failed
## How they buy
## Awareness
## Objections
## Language bank
[phrase] [link]

## Channels
Primary: [channel and why]. Secondary: [channel and why].

## Not the customer
## Guesses
[every line above that has no evidence behind it]
```

## A short example

This is a made-up profile to show the level of detail. A real one uses the user's research.

```
# ICP: solo mobile dog groomer, two to five years in, booked but losing money to no-shows

## The person
Works alone out of a van, 6 to 8 dogs a day. Books by text and Facebook messages.
Good at the work and bad at the admin, and knows it. Checks her phone between dogs,
never at a desk.

## What drives the purchase
A problem: unpaid gaps in the day from late cancellations.

## Their day
6:30 loads the van. 8:00 first dog. Phone in hand for 5 minutes between appointments.
1:00 lunch in the van, scrolls Facebook groups. 6:00 home, answers the day's messages,
this is when she would buy something.

## How they buy
Pays $30 to $60 a month for a booking app already. Decides alone, usually the same evening.
Trusts other groomers far more than a company.

## Objections
"My regulars will be offended if I ask for a deposit."
"I don't have time to learn another app."

## Channels
Primary: groomer Facebook groups. Secondary: Instagram.

## Not the customer
Salon owners with staff (need scheduling for a team). Hobby groomers with two clients a week.
```

## Rules

- Every line traces back to the research file or to something the user has seen first-hand. Anything else goes under Guesses.
- One profile per product. Add a second profile only when the data shows a clearly different buyer with different reasons and a different channel.
- Don't invent a name and a stock-photo life story. Details that came from nowhere make the profile feel real while making it less true.
- A profile that could describe a million people isn't finished. Keep narrowing.

## Keeping it updated

The profile gets better with every real conversation. After sales conversations, support messages and comment threads, add new objections and new phrases to the file and move items out of Guesses when evidence shows up. When the research skill re-scrapes, review the profile against the new data. When the best customers turn out to be different from the profile, change the profile to match the customers.

## Running this skill

When the user asks who to sell to: read the research file, run steps 1 to 6 and deliver `business/icp.md` with a three-line summary of the person, what drives them and where they are. When the user already has customers: start from the real ones. When writing or ads are underperforming: check whether the piece was written for this profile, and if the profile itself looks wrong, say so and fix the profile first. When the user asks only for the profile: deliver it as a standalone file, because it is used by every channel and not only by copy.
