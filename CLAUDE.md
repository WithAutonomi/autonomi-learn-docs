# CLAUDE.md — Autonomi Learn Documentation

This file controls how AI agents behave when writing, updating, or reviewing documentation in this repository.

## Repository purpose

This repo is the source of truth for the public Learn documentation on `docs.autonomi.com` and the main entry point to the wider docs site. It is synced to GitBook. All content is Markdown.

The goal of this repo is to help readers understand:
- what Autonomi is
- what it can and cannot do
- how it works at a conceptual level
- where to go next for node, token, and developer documentation

## Scope

This repo documents Autonomi 2.0 for a broad audience. It is not the place for SDK setup, API reference, or implementation walkthroughs unless a page explicitly links outward or contains a short `Under the hood` section.

Do not reference or verify against:
- Autonomi 1.0 or SAFE-era behavior unless the page is explicitly historical
- unmerged branches, open PRs, or expected future behavior
- old docs that conflict with current merged code
- repos outside the active source audit

## Audience and objectives

### Who these docs are for

- tech optimists and early adopters who discover emerging technology early and share it
- technically curious readers who are not assumed to be developers
- some developers, but never assume programming or protocol knowledge
- AI agents and LLMs consuming individual pages in isolation

### What these docs must enable

1. Understand what Autonomi is and what makes it different
2. Understand the main user-visible properties of the network
3. Understand important boundaries and limitations
4. Understand how the system works at a conceptual level without needing implementation detail
5. Find the right next path when the reader needs node, token, or developer documentation

### Priority hierarchy

Meaning comes before mechanism.

When deciding what to foreground, ask:
- Does this help a curious reader understand what Autonomi is, why it matters, or what it enables?
- Does this help an LLM restate the concept accurately from a single page?

If yes, it is first-class content. If not, it is supporting context.

Implementation detail is supporting context unless the page is explicitly about that detail.

## Source of truth

The default verification mode is current merged truth:
- verify against the latest merged commit on the default branch of the relevant source repos
- do not document branch-only or planned behavior as if it exists
- if a claim is not supported by current merged sources, remove it, reframe it, or label it explicitly as historical

### Source hierarchy

Use sources in this order:
1. Current merged code in the relevant Autonomi and Saorsa repos
2. Current merged Autonomi developer docs as a secondary synthesis aid
3. Existing Learn docs only as input to audit and rewrite, not as authority

Broad source repos:
- `ant-node`
- `ant-client`
- `ant-sdk`

Targeted source repos when needed:
- `saorsa-core`
- `saorsa-transport`
- `saorsa-pqc`
- `self_encryption`
- `evmlib`
- `ant-merkle`

Use `x0x` only when a page needs a clear storage-vs-realtime scope boundary.

### Required workflow

All documentation work follows `source audit -> draft -> verify`.

- Source audit: identify the claim, the likely source repos, and the exact facts that support it
- Draft: write only from audited evidence
- Verify: re-check every technical claim, named component, algorithm, protocol, and limitation before finalizing

### Refusal rules

- Do not document future behavior as present fact
- Do not preserve stale SAFE-era claims in ordinary Autonomi 2.0 pages
- Do not infer capability from naming, intent, roadmaps, or historical docs
- Do not let an older Learn page override current merged code
- If evidence is mixed or unclear, stop and ask

## Style guide

### Voice and tone

- Write in plain American English
- Prefer calm, direct, factual language
- Be clear without sounding academic
- Be confident without sounding promotional
- Use second person when it helps the reader, but neutral explanatory prose is fine for concept pages
- Explain why before how
- Lead with the product, concept, or reader outcome, not with repo names or implementation names
- Avoid time-relative wording such as `current`, `now`, `currently`, and `at present` unless the page is explicitly comparing versions
- Expand important acronyms on first use when that helps a first-time reader

### Avoid

Never use:
- `simply`, `just`, `obviously`, `of course`, `easy`, `easily`
- `leverage` (use `use`)
- `utilize` (use `use`)
- `it should be noted that`
- `in order to` (use `to`)

Avoid in normal Learn prose:
- manifesto language
- slogans
- grand claims about changing humanity or the future of the Internet
- company-marketing voice that speaks as `we` for the network

### Jargon and reader leveling

- Define unfamiliar terms on first use in plain language
- Do not open a page with algorithm names, acronyms, or internal component names unless the page is specifically about them
- If a technical term matters, explain what it means for the reader before naming the exact mechanism
- Prefer mental models and consequences over stack diagrams and internal architecture lists
- If an exact algorithm or protocol name is useful but optional, place it in a later section such as `How it works` or `Under the hood`

### Page structure

Every page must be self-contained.

Most concept pages should follow this order:
1. What it is
2. Why it matters
3. What it means for the reader
4. How it works
5. Under the hood (optional)
6. Related pages

Additional rules:
- One page, one main audience level
- Do not mix broad-reader explanation, developer setup, and protocol deep dive on the same page
- Link related pages at the end, not as hidden prerequisites
- Titles should describe user-facing outcomes or concepts, not internal mechanisms, unless the mechanism itself is the subject
- Glossary entries should be short, timeless definitions

### x0x and scope boundaries

- Define Autonomi clearly on its own first
- Mention `x0x` only when it prevents a misunderstanding or clarifies a boundary
- Do not present `x0x` capabilities as core Autonomi features
- When the boundary matters, state it plainly:
  - Autonomi is the permanent, immutable storage layer
  - `x0x` covers realtime, mutable, or collaborative behavior

### LLM and agent readability

- Assume an agent may read one page in isolation
- Put key definitions near first use
- Avoid ambiguous pronouns when the subject could be unclear
- Do not rely on images or diagrams as the only explanation
- Prefer short factual paragraphs over rhetorical flourishes
- If a page uses a figure, the surrounding text must still stand on its own

### Formatting

- Use ATX headers (`#`, `##`, `###`). Maximum depth: `###`
- One blank line before and after headers, lists, and code blocks
- No trailing whitespace
- Prefer standard Markdown
- Preserve existing GitBook-specific structures when editing a page that already depends on them
- Do not introduce new raw HTML unless GitBook requires it

## Terminology and naming

- Use American English spelling in all new or edited prose
- Preserve official capitalization for product names and protocols
- Expand important acronyms on first use when useful, for example `distributed hash table (DHT)` and `Autonomi Network Token (ANT)`
- Prefer plain-language descriptions before exact algorithm names
- Do not use repo names as primary framing in rendered prose unless the repo itself is the topic
- Use `post-quantum` precisely. Use it narrowly for explicit post-quantum cryptography such as node identity and transport, and more broadly only when you are clearly describing the overall threat model.

## Updating existing pages

1. Read the current page before editing
2. Make the minimum change that brings the page back into line with the source of truth and this style guide
3. Preserve working GitBook navigation, frontmatter, and card structures unless the task is to change them
4. Normalize touched text to American English and the Learn voice gradually; do not mass-rewrite untouched pages only for style
5. Remove or resolve stale notes such as `outdated`, `to be updated`, or `under construction` when you touch a page

## Reviewing pages

When reviewing a page or PR, check for:
- factual drift from current merged truth
- audience mismatch
- jargon overload
- unexplained acronyms
- `x0x` boundary blur
- leftover SAFE-era framing
- contradictions with other Learn pages
- stale diagrams, stale labels, or stale navigation
- overclaims or promotional wording
