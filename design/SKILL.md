---
name: design
description: Make everything the business shows look professionally designed - the web app, the landing page, the ad creatives, the thumbnails and the product images. Use when the user wants to build or redesign a web UI, needs the right component for a job (forms, tables, dashboards, AI or chat interfaces, marketing pages), wants a landing page layout, ad images, video thumbnails or a consistent brand look, asks about animations and transitions, or says their AI-built site looks generic. Contains the component map of shadcn/ui, COSS UI and Beautiful UI, the transitions.dev motion library, how to fetch any component's live code, the rules that keep a UI coherent, and the rules for ad creatives and thumbnails.
---

# Design

AI-generated design looks generic for one reason: the agent invents everything from scratch instead of using what professional designers already built. The fix isn't becoming a designer. It's working like a builder with a parts catalog: know what exists, pick the right part, fetch its real code, and adapt it to the project's foundation. This skill is that catalog, the assembly rules, and the same approach applied to ad creatives and thumbnails.

## Where this skill sits

This is the sixth of eight skills that work as a chain. Before designing, read `business/icp.md` (who is looking at this and on what device) and `business/context.md` (the tone, the offer and the Look section). If the Look section is empty, set the tokens in "Tokens before components" below and write them into the context file so every future session uses the same ones.

## Part 1: web UI

The libraries here are free to use, and each has a distinct job:

- **shadcn/ui**: the foundation. The default component system for React and Tailwind apps. Everything else layers on top of it. MIT.
- **COSS UI** (coss.com/ui): the polished app layer. Cal.com's design system, built on Base UI, with denser, production-tuned components. MIT. It is in early development, so expect occasional breaking changes.
- **Beautiful UI** (beautifului.dev): the AI-interface layer. Twenty carefully made components for agent products: chat, thinking states, approvals, streaming. MIT. If the app has an AI feature, its UI comes from here.
- **transitions.dev**: the motion layer. A curated collection of reusable CSS transitions with motion tokens and reduced-motion guards built in, plus its own official agent skill. The free tier is available by copy or CLI and a Pro tier sits behind sign-in.

### Rule zero: never invent what already exists

Before writing any component from scratch, check the maps below. If the component (or something close) exists, fetch its real code and adapt it. Hand-rolled versions of solved components (dialogs, comboboxes, date pickers, data tables) are where accessibility bugs, jank and the generic look come from. Building from scratch is reserved for interactions that are new.

### The component maps

**shadcn/ui: the foundation (ui.shadcn.com)**

Layout and structure: Sidebar, Resizable, Separator, Scroll Area, Aspect Ratio, Card, Sheet, Drawer, Tabs, Collapsible, Accordion.
Navigation: Navigation Menu, Menubar, Breadcrumb, Pagination, Command (cmd-k palette), Dropdown Menu, Context Menu.
Forms and input: Form (react-hook-form and zod wiring), Input, Textarea, Select, Combobox, Checkbox, Radio Group, Switch, Slider, Input OTP, Label, Button, Toggle, Toggle Group, Calendar, Date Picker, Field.
Feedback and status: Alert, Alert Dialog, Dialog, Sonner (toasts), Progress, Skeleton, Badge, Tooltip, Hover Card, Popover, Spinner, Empty.
Data display: Table, Data Table (TanStack wiring), Chart (Recharts wiring), Avatar, Carousel, Typography.

Use it for everything structural, every form, and any time no other library has a better version. Its blocks (ui.shadcn.com/blocks) also ship full sections: dashboards, login pages, sidebars.

**COSS UI: the polished app layer (coss.com/ui)**

Full set: Accordion, Alert, Alert Dialog, Autocomplete, Avatar, Badge, Breadcrumb, Button, Calendar, Card, Checkbox, Checkbox Group, Collapsible, Combobox, Command, Context Menu, Date Picker, Dialog, Drawer, Empty, Field, Fieldset, Form, Frame, Group, Input, Input Group, Kbd, Label, Menu, Meter, Number Field, OTP Field, Pagination, Popover, Preview Card, Progress, Radio Group, Scroll Area, Segmented Control, Select, Separator, Sheet, Skeleton, Slider, Spinner, Switch, Table, Tabs, Textarea, Toast, Toggle, Toggle Group, Toolbar, Tooltip. Plus hooks (useMediaQuery, useCopyToClipboard) and particles, which are pre-assembled patterns like auth forms and tables.

Use it for dense application UIs (dashboards, settings, admin panels) where the tighter Cal.com-style polish beats shadcn's defaults, and for components shadcn lacks or does less well: Autocomplete, Number Field, Segmented Control, Meter, Toolbar, Kbd, Frame, Input Group. It is built on Base UI and shadcn is built on Radix. Both can live in one app, but pick one library as the base for each surface and don't alternate per component, or focus behavior and design language drift apart.

**Beautiful UI: the AI-interface layer (beautifului.dev)**

Full set: Loading State (pixel-grid loaders with elapsed time), Thinking (expandable reasoning, search and coding traces), Streaming Text (streamed answers with inline sources and follow-ups), Approval Card (questions for the human before acting), Tool Chips (tool calls as compact chips), Task Rows (live agent task status), Chat (tabbed chat panel with composer), Prompt Bar (composer with @ sources, / commands, model picker, dictation), Recommendation Card (suggestion with confidence meter), Context Cards (retrieved knowledge chunks with sources), Diff Table (AI-proposed edits in tabular data), Records Table (CRM-style grid), Filter Table (status chips reorganizing live data), Sidebar Nav (collapsible workspace and chat nav), Search (command search with empty state), Flowchart (workflow trigger and condition canvas), Insight Cards (paged insights with live charts), Code Block (line-numbered listing and diff), Fine-tune Card (inspector-style property controls), Selection Actions (highlight to rewrite).

Use it for any AI-native surface. Never hand-roll a thinking state, a streaming answer, an approval flow or a tool-call display. These twenty solve exactly those problems.

**transitions.dev: the motion layer (transitions.dev)**

Free transitions, each a self-contained CSS snippet with semantic custom properties, namespaced classes and a prefers-reduced-motion guard: Card resize, Number pop-in, Notification badge, Text states swap, Menu dropdown, Modal open/close, Panel reveal, Page side-by-side, Icon swap, Success check, Avatar group hover, Error state shake. More exist behind the Pro sign-in.

Use it for every micro-interaction in the app. Adopt its motion tokens as the project's single motion system and pull every transition from here instead of improvising easings per component.

This library has no open-source license on its code, so its snippets are used in projects (that is what the site offers them for) but never redistributed inside other products, skill files or component packs. Fetch per project and don't bundle.

### Fetching the code

The maps say what exists. The code always comes fresh from the source:

- **shadcn/ui:** `npx shadcn@latest add [component]` installs into the project with dependencies. Raw component JSON lives at `https://ui.shadcn.com/r/[component-name].json`. The shadcn MCP server (`npx shadcn@latest mcp init`) gives agents browse, search and install, and `https://ui.shadcn.com/llms.txt` indexes the docs for agents.
- **COSS UI:** docs index for agents at `https://coss.com/ui/llms.txt`, each component's docs and code at `https://coss.com/ui/docs/components/[component-name]`, and the repo at `github.com/cosscom/coss`.
- **Beautiful UI:** copy from `https://www.beautifului.dev/` (each numbered component links to its code). License at `https://www.beautifului.dev/license`.
- **transitions.dev:** copy buttons on `https://transitions.dev/` give the full snippet. CLI: `npx transitions-pro add [name]` and `npx transitions-pro list`. Its official agent skill installs with `npx skills add Jakubantalik/transitions.dev`, and when that skill is installed, motion questions defer to it.

The workflow: identify the need, find it in the maps, fetch that component's current code, adapt it to the project's foundation. Fetch only what the task needs.

### The integration rules

Good components can still add up to a generic result when the parts don't agree with each other. These rules keep the assembly coherent:

1. **One foundation, declared once.** The project picks its base (usually shadcn) and its accent libraries, and writes that decision down in the repo (a DESIGN.md or a comment block in the global CSS) and in the Look section of `business/context.md`.
2. **Tokens before components.** Before importing anything, set the design tokens: the neutral scale, one accent color, the radius value, the font pair (one for UI, optionally one for display) and the spacing rhythm. Every fetched component gets pointed at these tokens on arrival.
3. **Adapt on arrival, not later.** The moment a component lands, swap its colors to the project's variables, match the radius and the spacing scale, and strip variants the app won't use.
4. **Density is a decision.** Marketing pages breathe, with generous spacing and larger type. App surfaces are dense, with tight spacing and more per screen. Pick per surface and hold it.
5. **One motion language.** Animations come from one source and one duration and easing scale. Use less motion than feels fun, keep transitions under about 200ms, and animate only entrances, exits and state changes that need explaining.
6. **Contrast and hierarchy over decoration.** If a screen looks bland, the fix is almost never a gradient. It is stronger type hierarchy, more whitespace or one deliberate accent. Delete decoration before adding it.
7. **States are part of the component.** Every interactive element ships with hover, focus-visible, disabled, loading, error and empty states. Deleting them during adaptation is a regression.
8. **Dark mode from the tokens.** If the app supports it, both modes come from the same token layer on day one.
9. **Don't break accessibility.** These libraries' keyboard navigation, focus management and ARIA are the hard part. Adaptations touch classes and tokens, not the structural markup and handlers.
10. **Take composition from elsewhere, not components.** Inspiration sites inform layout and feel. The code still comes from the libraries above. Cloning someone's actual design from a screenshot is off the table.

### Assembly recipes

- **Landing page:** shadcn primitives with the density opened up, one display font, one accent and generous whitespace. See the landing page section below.
- **SaaS dashboard:** shadcn Sidebar, Data Table, Chart and Card. COSS Segmented Control, Number Field and Meter for the dense controls. Sonner for toasts and skeletons on every async region.
- **AI product:** shadcn foundation. Beautiful UI Chat or Prompt Bar as the core surface, Thinking, Tool Chips and Streaming Text for the response area, Approval Card for human approval, Task Rows for background work.
- **Internal tool or admin:** COSS UI as the surface layer, shadcn Data Table for the grids, Command for power-user navigation.
- **Forms anywhere:** shadcn Form wiring (validation included) or COSS Field and Fieldset. Never hand-rolled validation UI.

### Landing pages

A landing page has one job, which is getting the visitor to the call to action, so its design is mostly about removing things.

- **Section order follows the copy.** Headline and subhead, proof, the problem, how it works, what they get, questions, price, with the call to action repeated. The writing skill supplies the words in that order.
- **The first screen carries the page.** Above the fold on a phone: the headline, one line under it, the call to action and one piece of proof or a picture of the product. If a visitor read nothing else, they should know what this is and who it is for.
- **Phone first.** Most visitors arrive from social on a phone. Build and check the mobile layout before the desktop one, with buttons large enough to tap and text readable without zooming.
- **One accent, used for one thing.** The accent color belongs to the call to action. If everything is highlighted, nothing is.
- **Show the product.** A real screenshot, a real page of the guide or a real before and after beats an illustration. Avoid stock photos.
- **No navigation that leads away.** A sales page has no menu full of links. The only way forward is the button.
- **Fast.** Compress images and avoid heavy animation. A page that takes several seconds to load loses the visitor the ad or post just paid for.
- **Proof next to claims.** Each testimonial or number sits beside the claim it supports.

## Part 2: ad creatives, thumbnails and images

The same idea applies outside the browser: start from what already works for this audience, then adapt it to the brand.

### Start from the swipe file

The research skill collects the niche's best-performing posts, long-running ads and outlier video thumbnails under "What already works in content". Before making anything, look at what they share: face or object, how much text, which colors, which format. Study the patterns and never copy an image. Also note what everyone in the niche is doing, because a creative that looks like all the others gets scrolled past.

### One idea per image

A creative has about two seconds. It should make the viewer ask a question that only clicking answers: how is that possible, or what happens next. An image that only illustrates the topic loses to one that opens a question.

### Rules that hold across ads and thumbnails

- **Faces work.** A close-up face with a clear emotion connects, and the eyes matter most. Push the emotion slightly past natural, because at feed size a subtle expression reads as blank.
- **Face plus object** when there is a thing to show. The reaction next to the interesting object is the most reliable general format. **Object only** when the thing itself is the star: large, centered, with no doubt about where to look.
- **Tell it without words.** If the image can't say it alone, add three or four words at most, and never the same words as the headline or title beside it.
- **Composition.** Put the subject on a rule-of-thirds point.
- **Color.** Use opposite colors so subject and background separate hard, and check the image against both a white and a near-black app background so it doesn't disappear into either.
- **Check it at phone size, in context.** Take a screenshot of a real feed or search page and place the creative among the others. If anything is too small to read, redo it. Then glance at it for a fraction of a second and note what registered. That is all a scrolling viewer gets.
- **Honest.** A dramatic image is fine when the product or video delivers exactly what it shows. A creative that promises something that isn't delivered brings clicks that turn into refunds or early exits.

### Formats to choose from

Face with strong emotion. Face plus object. Object only. Two faces either side of an object. Before and after in two panels. Three panels showing a progression. Something very big or very small next to a person. Action frozen mid-moment. A mass of one thing with the subject standing out of it. Arrows and circles to direct the eye, used sparingly.

For ads specifically, these types cover most of what works: a real-looking phone video of someone using or reacting to the product, a screen recording of the product doing the job, a before and after, a customer quote as the image, and a plain image with one strong headline.

### Sizes

- Vertical video and stories (TikTok, Reels, Shorts, Stories): 9:16, 1080 by 1920.
- Feed images and feed video: 4:5 (1080 by 1350) or 1:1 (1080 by 1080).
- YouTube thumbnails: 16:9, 1280 by 720.

Keep text and faces away from the top and bottom edges of vertical video, where the app's own buttons and captions sit.

### Making them

Use an image model such as GPT Image or Nano Banana for stills and a video model such as Seedance, Veo or Kling for clips, through their own apps or an API layer like Replicate or Fal.

A prompt that gets a usable image names the subject, the setting, the framing, the light and what must not be in it:

```
photo of [subject] [doing what], in [setting]. shot on a phone, [close / medium] framing,
subject on the left third, [warm / cool] natural light. background is [color, simple].
no text, no logos, no extra people.
```

- For product shots, give the model the real product photos so the picture matches what the customer receives.
- Add text and logos afterwards in an editor or in code. Image models still garble lettering.
- Label AI presenters as AI where the platform requires it.
- Never generate a real person's likeness or another brand's assets.

### Keep the brand consistent

Use the accent color and fonts from the Look section in every creative so returning viewers recognise the business at a glance. A consistent accent across thumbnails does the same job on a channel page.

### Always make variants

Two or three different concepts per ad or thumbnail, not three versions of one concept. Change the idea, not the shade of blue. The marketing skill tests them against each other, and the winner's pattern goes into the what-worked log in `business/context.md`.

## Running this skill

When the user asks to build a UI: establish or read the foundation (tokens, base library, density) first, then map every screen element to a component from the maps, fetch the live code for each, adapt it to the tokens, and only build from scratch what the maps lack. When the user brings a generic-looking site to fix: diagnose against the integration rules (usually mixed foundations, default palettes, no hierarchy or too much motion), then re-map the screen to real components and rebuild surface by surface. When the user asks which component to use: answer from the maps with the library and name, and give the fetch command. When the user asks for creatives or thumbnails: read the swipe file and the Look section, then deliver two or three distinct concepts with the image prompts or the finished images. Always say which library each UI piece came from, because the MIT libraries want their attribution to travel with the code and transitions.dev snippets are never redistributed onward.
