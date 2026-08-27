# aespa Wire

An independent, unofficial English-language fan hub for aespa/MY — news translation, album reviews, official-only video curation, a timezone-aware world tour schedule, and a fan quiz, built to run on Google AdSense.

**Not affiliated with, endorsed by, or sponsored by SM Entertainment or the members of aespa.**

## What's in this repo

This is a single static page — `index.html` — with everything (HTML, CSS, JS) inlined. No build step, no dependencies, no backend. It's meant to be served as-is by GitHub Pages. This repo follows the same template as [Bangtan Wire](https://fhzl0117-hue.github.io/bangtan-wire/), [Blackpink Wire](https://fhzl0117-hue.github.io/blackpink-wire/), and [Stray Kids Wire](https://fhzl0117-hue.github.io/stray-kids-wire/) — part of the "Wire" series, one dedicated site per artist.

The page is organized into six "desks," each mapped to a content pillar:

| Desk | Section id | What it does |
|---|---|---|
| 01 · News | `#news` | Translated & summarized news dispatches, each linking to its original source |
| 02 · Review | `#reviews` | Album / track reviews, text only |
| 03 · Screening Room | `#screening` | Official YouTube embeds only — never re-uploaded video |
| 04 · Signal | `#signal` | Release/tour schedule with a live countdown, auto-converted to the visitor's local timezone |
| 05 · Quiz | `#quiz` | A lightweight interactive quiz, no backend, no data collection |
| 06 · Market | `#market` | Links to official stores/tickets (affiliate links go here) |

## manifest.json — K-Wire Network auto-discovery

This repo carries a `manifest.json` at its root so it's automatically picked up by [K-Wire Network](https://fhzl0117-hue.github.io/), the directory hub for the whole "Wire" series. No manual edit to the hub repo is needed — its page fetches this file on every visit and lists this site automatically. If a member solo subpage is ever added here, add it to this file's `members` array and it will be merged into the hub's card automatically too.

## Updating content

Everything is plain HTML — open `index.html` in any editor and look for the section with the matching `id` (e.g. `<section ... id="news">`) to update copy. There's no CMS yet; each dispatch, review, or tour date is a hand-edited block. See the comments inside the `<script>` tag at the bottom for how the quiz and countdown timers work if you need to change their logic.

**Before adding new tour dates or news items,** verify the underlying facts against a real source and keep the "Read the original source" link pointing at it — that link is what keeps this page compliant with content policies (Google AdSense does not allow re-publishing copyrighted material, and this page's whole design is built around linking out and summarizing instead of reposting).

**Before adding any new YouTube embed,** verify it against the official channel using the oEmbed check: fetch `https://www.youtube.com/oembed?url=https://www.youtube.com/watch?v=<ID>&format=json` and confirm `author_name` matches SMTOWN (or the group's own verified channel) — a search result titled "(Official Music Video)" is not proof by itself. This caught several fan-reuploads during this site's initial build and must be applied to every future embed.

## License / ownership

Internal company project. Not licensed for redistribution outside the team without checking with whoever owns this repo.
