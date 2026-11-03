# Adobe Experience Platform Documentation: Copilot Instructions

This repo (`experience-platform.en`) is Adobe Experience Platform public documentation.
Every piece of content you draft, edit, or review MUST follow the rules below.

## Do not narrow or reframe requests

Answer the request that was actually made, not a smaller one. Do not restate a request
as smaller than it was, and do not hand back a partial job described as complete.
Every line in this repo can be fixed regardless of who or what wrote it or when — "pre-existing,"
"not part of this diff," and "out of scope" are not reasons to leave a violation unfixed.
When asked to fix violations, fix all of them, however old. If something genuinely blocks
the work, say exactly what and what is left undone, and stop.

## 1. Voice, tone, and style

### User-focused writing

Center the user, not the feature. Write what the user can **do**, not what the feature does.

- Use second person ("you") and imperative mood for instructions.
- Use "you" when speaking to the audience about themselves, not "users." "Users" is
  acceptable when referring to a role (e.g., an admin managing users).
- Avoid "Feature X allows you to…" or "Feature X enables you to…". Put the user as the
  subject or use imperative mood.
  - Bad: "The Server API can be used on servers." Good: "Use the Server API on servers."
  - Bad: "Calculated fields allow for values to be created…" Good: "Use calculated fields
    to create values…"
- Watch for overuse of "you can." It is fine but can create repetitive or wordy sentences.
- Use "select" for choosing options from a list or highlighting text. Use "click" only for
  explicit mouse actions. Avoid naming the control type (button, link) unless needed for
  disambiguation.
- Use "Open" / "Close" for applications and major windows or panels.
- Use "Leave" for leaving a site or experience (e.g., "Leave Report Builder").
- Use "go to" or "navigate to" for navigation.
- Use "Play video," not "Watch video."
- Use "View," "Show," or "Go to all," not "See all."
- Use "sign in" / "sign out," not "log in" / "log out."
- Avoid "in order to." Use "to" instead.
- Avoid "utilize." Use "use" instead.
- Avoid vague adjectives like "fast" or "easy." Be precise: "This process usually takes
  5 minutes."
- Avoid weak adverbs: very, extremely, incredibly.

### Sentence and paragraph structure

- Target 20 words or fewer per sentence (35 max). One thought per sentence.
- Paragraphs: max 125 words, ideally 100 or fewer. Max 4 to 5 sentences. No walls of text.
- Use active voice. Avoid passive constructions and nominalizations (e.g., "create" not
  "creation").
- Use simple subject-verb-object structure.
- Avoid false subjects ("It is…", "There are…").
- Use the same word consistently. Do not rotate synonyms.
- No humor, slang, jargon, or culture-specific examples (must localize well).
- Use the Oxford comma in lists of three or more items.
- Spell out whole numbers zero through nine; use numerals for 10 and above.
- No semicolons. Use a period and a new sentence instead.
- Do NOT use em dashes, en dashes, or hyphens in prose. Rephrase instead. Hyphens are
  permitted only in compound adjectives that appear in the UI, file names, and code.
- Do NOT use horizontal rules (`---` or `***`). They are not supported in Experience League.

### Scannability

- Readers should grasp the article scope from title, headings, and captions alone.
- Max 2 to 5 subsections per section.
- Target 7 steps per task; 10 is the practical maximum. Break longer procedures into subtasks.
- Max 8 items per bulleted list.
- Use tables when they make term/definition lists easier to scan.
- Content should score below grade 10 on a readability test (after removing proper nouns
  and titles).

### Writing for AI discovery

- Put key terms (product names, feature names, tasks) in body text and link text, not only
  in images or complex tables.
- Write clear, self-contained headings and first paragraphs.
- Keep sentences short and direct.
- Use structured formats (numbered steps, short bullets, definition-style headings) for
  procedures and comparisons.
- Include synonyms or alternate terms on first use (e.g., "ECID (Experience Cloud ID)").
- Keep metadata fields (title, description, feature tags) complete and accurate.

## 2. Localization tags (always apply)

Machine translation runs automatically on every commit to main.

### `[!DNL Product Name]`: Do Not Localize

Apply to Adobe product names (`[!DNL Analytics]`, `[!DNL Target]`, `[!DNL Campaign]`,
`[!DNL Experience Platform]`), third-party product names (`[!DNL Mozilla Firefox]`,
`[!DNL Workfront]`), functional names that could confuse translation (`[!DNL Pass]`,
`[!DNL Campaign]`), and Boolean operators used as logical terms (`[!DNL AND]`, `[!DNL OR]`).

Do NOT apply to URLs, file names, directory names, code blocks, acronyms, or terms already
in the Do Not Translate database.

In link text, remove the tag brackets: `[Adobe](https://www.adobe.com)`, not
`[[!DNL Adobe]](https://www.adobe.com)`.

### `[!UICONTROL Label]`: UI controls

Mandatory on every clickable UI element in procedure steps, and on feature names,
navigation elements, page names, options, fields, and tabs as shown in the interface.

- Bold in steps and navigation: `Select **[!UICONTROL Destinations]** from the left navigation.`
- Italics acceptable in conceptual (non-step) text for clarity.
- In HTML tables: use `<span class="uicontrol">term</span>` instead of `[!UICONTROL]`.
- In link text: remove the tag brackets.
- Capitalization must match the interface exactly.
- Do NOT apply to generic terms used conceptually ("segment," "metric," "campaign") unless
  referring to the UI element, long sentences, code blocks, acronyms, or icon descriptions
  (use the icon's hover/tooltip name if available).

### `[!DONOTLOCALIZE]`: exclude entire sections

```markdown
>[!DONOTLOCALIZE]
>
>Content that must not be translated.
```

Not needed inside code blocks; those are not localized by default.

### Where tags can and cannot be used

- Can be used in: paragraphs, lists, headings, tables, badges, alt text, and metadata.
- Cannot be used in: code blocks, acronyms.
- If a metadata field begins with a `[!DNL]` or `[!UICONTROL]` tag, enclose the entire field
  value in quotation marks or validation fails.

## 3. Terminology and branding

### Product names

Always use these exact forms. Include "Adobe" on first reference in a guide. Do NOT precede
product names with "the" unless the official name includes it.

| Correct | NEVER use |
|---|---|
| Adobe Experience Platform | AEP, AXP, Adobe XP, Adobe Cloud Platform |
| Experience Platform (secondary reference) | Platform (alone, unless context is unambiguous) |
| Adobe Real-Time CDP | RTCDP, ARTCDP |
| Real-Time CDP (secondary) | Real-time CDP (lowercase "t") |
| Adobe Real-Time Customer Data Platform | — |
| Real-Time Customer Profile | Real-time Customer Profile, Unified Profile |
| Adobe Journey Optimizer | AJO |
| Adobe Customer Journey Analytics | CJA |
| Customer Journey Analytics (secondary) | — |
| Adobe Real-Time CDP Collaboration | RTCDP Collaboration, RTCDP Collab, Collab |
| Adobe Real-Time CDP Connections | RTCDP Connections, AEP Connections, Connections (alone) |
| Adobe Experience Platform Edge Network | Platform Edge Network, Platform Edge, Adobe Experience Edge |
| Tags (product name) | Launch (deprecated) |
| Decision Management | Offer Decisioning (parenthetical only: "formerly Offer Decisioning") |
| datastream (one word, lowercase) | datastreaming, edge configuration |
| Analysis Workspace | analysis workspace, workspace, Workspace |
| Adobe AI | Sensei (deprecated) |
| Adobe GenAI | — |
| Adobe GenStudio for Performance Marketing | — |

- "Real-Time" always uses capital R and capital T when part of a product name.
- "Editions" is lowercase generically; "Edition" is capitalized as part of a product edition
  name (e.g., "Adobe Real-Time CDP B2C Edition").
- Do NOT abbreviate product names in user-facing documentation (no AEP, CJA, AJO, RTCDP).
  Limited exceptions: acronyms may appear parenthetically on first use for SEO, or in TOC
  entries, description metadata, and headings where length is a concern.
- Analytics capitalization: panel names are lowercase (blank, attribution, experimentation,
  freeform; exception: "Journey canvas"). Visualization names are lowercase (bar, donut,
  histogram, line, tree map, text).

### Feature and concept terminology

| Correct | Do NOT use |
|---|---|
| event forwarding | server-side forwarding, Launch Server Side |
| allowlist | whitelist |
| denylist / blocklist | blacklist |
| primary / replica OR primary / secondary (servers) | master / slave |
| main (GitHub branch) | master |
| ethical hacker | white hat hacker |
| remarketing | retargeting |
| field group | mixin (deprecated), Extensions, Mixins |
| automatic data expiration | TTL, time-to-live, expiry |
| non-production sandbox | staging (as an environment name) |
| segment definition | segment (alone, when meaning the definition) |
| ID (always capitalize) | Id |
| ingestion / ingest / ingested | onboarding (for adding data to Platform) |
| dataset / datasets | Data File, dataset files |
| access control | permissions (for the Platform feature) |
| widget | metric card (deprecated) |
| placeholder variable | dummy variable |
| unavailable / locked / turned off / deactivated | grayed out |
| coherence check | sanity check |
| built-in | native (as a synonym for built-in) |
| high priority | must nail |
| legacy | grandfather clause |
| primary / main / source | master (as a descriptor) |

### Internal-only terms: NEVER use in public-facing docs

| Internal term | Use instead |
|---|---|
| AEP | Adobe Experience Platform |
| PALM | sandbox management / access control |
| BIOME | environment |
| Hydrate / hydration | create / populate |
| Unified Profile | Real-Time Customer Profile |
| Staging (environment) | non-production sandbox |
| DTM | Tags |
| Tenant | IMS org / organization |
| CRUD | create, read, update, and delete (spell it out) |
| Siphon, BSO, Ethos | internal code names, never external |
| Hops | internal GDPR/access control term |
| Pacing | non-user-facing advertising term |
| Pipeline | internal Adobe infrastructure term |

## 4. Inclusive language and accessibility

### Inclusive language principles

- Use gender-neutral terms: "sales representative" not "salesman," "moderator" not "chairman."
- Prefer second person ("you") to avoid gendered pronouns.
- Use singular "they" for a person whose gender is unknown. Do NOT use he/she or (s)he.
- Include names from non-white cultures in examples (e.g., Ayesha, Ibrahim, Vignesh, Quynh).
  Do NOT use only culturally white names.
- Do NOT conflate sex (male/female) with gender (man/woman).
- Capitalize nationalities, peoples, races (other than "white," per AP Stylebook), and tribes.
- Use person-first language: "people who use assistive technology," not "the disabled."
- Avoid euphemisms like "differently abled." Avoid descriptors used as nouns: "the blind,"
  "the deaf."
- Avoid terms that reflect identity/cultural appropriation: spirit animal, Sherpa, pow wow,
  guru, ninja, tribe.

### Non-inclusive terminology to avoid

| Use | Not |
|---|---|
| allowlist / denylist / blocklist | whitelist / blacklist |
| primary / replica OR primary / secondary | master / slave |
| main (git branch) | master |
| high priority | must nail |
| placeholder variable | dummy variable |
| unavailable / locked / turned off / deactivated | grayed out |
| coherence check | sanity check |
| built-in | native (as a synonym) |
| authority / expert | guru / ninja |
| members of your group | members of your tribe |
| meeting | pow wow / circle the wagons |
| role model / kindred spirit | spirit animal |
| guide | Sherpa |
| legacy | grandfather clause |
| futile undertaking | death march |
| ridiculous / incompetent / unpredictable | dumb / lame / crazy |
| ethical / unethical hacker | white hat / black hat hacker |
| Play video | Watch video |
| View / Show / Go to all | See all |

### Accessibility: describing the UI

Do NOT describe UI elements by color or screen position. Use chronological, not spatial,
language:

| Use | Not |
|---|---|
| First, Next, Finally | Above, Below |
| In the menu bar | On the left |
| Before / After | At the top / bottom of the screen |

Describe what controls do, not what they look like:

| Use | Not |
|---|---|
| Select Search | Click the magnifying glass icon |
| Edit | The pencil icon |
| On / Off | Switch / toggle / activate |
| Menu | Side drawer |
| Enter email | Type your email address |
| Save | The "Save" button |
| Cancel | Close |

Do NOT use color alone to convey information. Always pair color with text or shape.

### Accessibility: alt text, links, and videos

- **Alt text**: describe what the image shows, not just its screen name. Use complete
  sentences, full words (screen readers spell abbreviations), and include relevant text
  from the image. Images that convey information independent of surrounding text MUST have
  alt text.
- **Links**: never use "click here" or "link" as link text. Make the destination clear from
  the link text alone.
- **Videos**: must NOT autoplay. Always provide a text alternative, transcript, or link to
  written instructions. Include meaningful captions.

## 5. Markdown syntax essentials

### Frontmatter (required on every file)

```yaml
---
title: Title Case Title Here
description: Learn how to... or Learn about... (150-160 chars, sentence case).
---
```

- Do NOT add `exl-id` when creating a new page. It is generated automatically at publishing
  time. Only preserve `exl-id` fields that already exist on existing pages.
- Title: title case, max 60 characters, no pipe or product name (added automatically).
  Concept titles are noun phrases; task titles are verb phrases.
- Description: sentence case, 150 to 160 characters. First sentence summarizes; second is a
  call to action. Do NOT begin with the product name or copy the first paragraph verbatim.

### Headings

- `#` = H1 (one per page, first line after frontmatter). `##`, `###` for subsections. Never
  skip levels.
- Target 5 words or fewer, max 69 characters. Blank line before and after every heading.
- Every heading must be followed by body text; never stack headings or place a list/table/note
  directly under a heading.
- Sentence case. Concept headings are noun phrases; task headings are imperative verbs
  (avoid gerunds).
- No single-word abstract headings ("Overview," "Introduction") without describing the topic.
- Custom anchor IDs: `## Section title {#section-id}` (lowercase, hyphenated).

### Links, images, and code

- Internal cross-references use root-relative paths: `[text](/help/path/to/file.md)`.
  External links use absolute `https://` URLs.
- Never use "click here" or "link" as link text. Avoid raw URLs in body text.
- Alt text: `![alt text](path/to/image.png)`. Full sentences, no leading "This image shows...".
- Screenshots: Light theme only, no customer data, no third-party UI, no images of code.
- Fenced code blocks use triple backticks with a language identifier. Code blocks are not
  localized (no DNL/UICONTROL needed inside them).
- Videos: `>[!VIDEO](url?quality=12&learn=on)`. Never autoplay; always provide a transcript
  or written alternative.

### Admonitions

```markdown
>[!NOTE]
>
>Note content here.
```

A blank `>` line must separate the tag line from the content; every continuation line starts
with `>`. Do NOT place a `[!NOTE]` immediately after a `[!CONTEXTUALHELP]` block.

### Contextual help popovers (`[!CONTEXTUALHELP]`)

`[!CONTEXTUALHELP]` blocks feed popover tooltips that engineering wires into the Experience
Platform UI. They live in the docs but render as in-product popovers via a JSON feed
generated at build time.

```markdown
## Configure file names {#configure-file-names}

>[!CONTEXTUALHELP]
>id="platform_destinations_activate_filename"
>title="Configure file name"
>abstract="For file-based destinations, a unique file name is generated per segment. Use the file name editor to create and edit a unique file name or keep the default name."
>additional-url="https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/activate-batch-profile-destinations.html#file-names" text="Learn more in documentation"
```

Required fields: `id`, `title`, `abstract`. Everything else is optional.

**Placement:**
- The block must come directly after a heading (`#`, `##`, or `###`) that has an explicit
  anchor ID (e.g., `### Section title {#section-id}`). No paragraph or other content between
  the heading and the block, or the popover won't render.
- Multiple `[!CONTEXTUALHELP]` blocks can appear consecutively in the same section (e.g.,
  one per field being documented).
- Do NOT place a `[!NOTE]` block immediately after a `[!CONTEXTUALHELP]` block. It breaks
  rendering on Experience League (known platform limitation).

**ID syntax:**
- Format: `id="platform_<yourarea>_<workflow>_<uiitem>"`, e.g.
  `id="platform_destinations_activate_deduplicationkey"`.
- IDs can contain capital letters.
- IDs must be unique across the doc set (checked at build time). The same ID can be reused
  across multiple UI locations by engineering, which produces identical popover content in
  each spot. That's expected.

**Links inside a popover, use `additional-url`, not inline HTML:**
- To add a link, use a separate line: `>additional-url="URL" text="Link text"`. Do NOT embed
  `<a href="...">` or markdown `[text](url)` inside the `abstract` string for this purpose.
- The `additional-url` value MUST include `.html` in the path or the link will not display in
  the UI (e.g., `https://experienceleague.adobe.com/docs/experience-platform/path/to/page.html#anchor`,
  not the newer `/en/docs/...` extensionless form used in body-text links elsewhere).
- Maximum of two `additional-url` lines per block.
- A first link is auto-generated from the section heading during the Jenkins build. You
  don't add that one manually, and you cannot rename it.

**Other supported syntax:**
- The `abstract` field supports basic HTML/markdown for emphasis and structure: `<b>`,
  `<br>`, `<ul><li>`, `**bold**`.
- Video links are supported via the same `additional-url`/`text` mechanism, pointing to a
  direct video URL or YouTube URL.

**Workflow note:** when handing a new popover ID to the UI/engineering team (usually via a
Jira ticket), also provide a fallback URL (prefer a goURL if one exists for that page) and
the UI location. This fallback is separate from the `additional-url` used in the docs
markdown.

### Lists and tables

- Use `*` or `-` consistently within one article; don't mix.
- Numbered lists use `1.` for every item. Single-step procedures use a bullet, not `1.`.
- No GitHub-style task list checkboxes (`- [ ]`); not supported in Experience League.
- Surround lists and tables with blank lines. Keep list items grammatically parallel.

### File and folder naming

- Markdown filenames: lowercase with hyphens, no capitals/underscores/periods/spaces.
- Use descriptive slugs (`create-calculated-metric.md`), not bare names like `overview.md`.
- Images go in an `assets/` subfolder; images that must not be localized go in
  `do-not-localize/`.

## 6. Structure and TOC conventions

- Three content types, kept separate: **Concept** (what/why, noun headings), **Task**
  (how, imperative headings, always preceded by a concept), **Reference** (fields,
  parameters, tables).
- Steps: each is a single complete sentence starting with a verb or the goal. Target 7
  steps per task, 10 max; break longer procedures into subtasks.
- TOC.md: sentence case entries, valid anchor IDs on every section heading, no duplicate
  file entries, no mid-list comments.
- Hide a page from navigation with `{hide-from-toc}` in `TOC.md` (not frontmatter). Hide
  from search engines with `hide: true` in frontmatter.
- Branch naming: no username prefix. Use the Jira ticket number and a title-cased slug
  (e.g., `PLAT-12345-Update-Guardrail-Limits`). Name the branch and PR title the same way.

## 7. Spelling and punctuation

- American English spelling: color, recognize, license, while, expiration, meter, among
  (not colour, recognise, licence, whilst, expiry, metre, amongst).
- Reserve quotation marks for quoting people; don't quote UI strings (use bold +
  `[!UICONTROL]` instead).
- Use italics for terms used as terms (*profile*, not "profile"). Use backticks for code,
  parameters, file names, and typed text.
- Bold only for UI elements in procedures (with `[!UICONTROL]`) and key terms at first
  introduction.
- No semicolons, no em/en dashes/hyphens in prose, no horizontal rules (see section 1).

## 8. Review checklist

Before finishing any edit, verify:

- User-focused voice, active voice, second person, no "allows you to"/"enables you to"
- Sentences ≤20 words, paragraphs ≤125 words
- Headings: sentence case, ≤5 words/69 chars, followed by body text, no skipped levels
- Correct product names and forms; no deprecated, internal-only, or non-inclusive terms
- `[!UICONTROL]` on every UI element in steps; `[!DNL]` on every product/third-party name
- No tags inside code blocks; tagged metadata fields wrapped in quotation marks
- Correct admonition syntax; consistent list markers; no task lists; no horizontal rules
- Alt text is descriptive and complete; no "click here"; no spatial/directional language
- No color used alone to convey information; videos don't autoplay
- Required frontmatter present; root-relative internal links; lowercase hyphenated filenames
