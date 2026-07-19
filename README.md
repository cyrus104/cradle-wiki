# Willverse Wiki — content mirror

The complete content of the **Willverse Wiki**: a spoiler-safe, source-grounded fan
encyclopedia for **Will Wight's connected universe** — *Cradle*, *The Traveler's Gate
Trilogy*, *The Elder Empire*, and *The Last Horizon* — exported from the live MediaWiki as
**one file per page**.

> ~6,400 pages · 26 books across 4 series · 35,000+ facts, each cited to book and chapter ·
> every direct quote verified verbatim against the text

## What makes this wiki different

- **Grounded.** Every fact on every page carries an inline citation to the book and chapter
  that reveals it. Direct quotes are verified word-for-word against the source before they
  can be published; article prose is original summary, never copied text.
- **Spoiler-safe.** Spoilers are gated **per series, per book**: a reader sets how far
  they've read in each series independently, and anything past that point stays hidden.
  Even auto-applied category labels follow the policy — only facts from a character's
  introduction book may label a page.
- **Coppermind-inspired structure.** Category poly-hierarchy with curated portals
  (characters by series, by group, by calling; locations by kind; lifeforms; culture),
  per-entity timeline pages, per-series footer navigation, magic-system overviews, and book
  hub pages indexing everything that appears in each novel.

## Repository layout

| Path | Contents |
|---|---|
| `main/` | Articles — characters, locations, groups, events, artifacts, concepts, timelines, book hubs |
| `categories/` | Category pages (the browsing tree: portals, facets, series umbrellas) |
| `templates/` | Templates (spoiler gate, infoboxes, navboxes, stub banner) |
| `mediawiki/` | Site interface pages (the per-series spoiler gadget, sidebar) |
| `project/` | Project pages (About) |
| `files/` | File description pages (book covers) |
| `images/` | Uploaded images (cover art, logo) |

Files are raw **MediaWiki wikitext** (`.wiki`). Page titles are percent-encoded where they
contain filesystem-unsafe characters (`urllib.parse.unquote` recovers the exact title).

## How this repo is generated

This is a **one-way mirror**: the wiki is the source of truth, and an export tool writes it
here — full-tree sync, one commit per export — so **each commit is a reviewable diff of what
changed on the wiki**. The pipeline that builds and seeds the wiki (local LLM + RAG over the
books, extraction → verification → judging → rendering) lives in the companion repo:
**[cradle-wiki-builder](https://github.com/cyrus104/cradle-wiki-builder)**.

Because exports overwrite this tree, edits should happen on the wiki itself rather than as
pull requests here — a PR against these files would be clobbered by the next export.

A wiki can be restored from this mirror (or from database backups) — see
`mediawiki/SETUP.md` in the builder repo for the procedure.

## Copyright

This is an **unofficial fan project**. All rights to *Cradle*, *The Traveler's Gate
Trilogy*, *The Elder Empire*, *The Last Horizon*, and their characters and settings belong
to **Will Wight and Hidden Gnome Press**. This wiki publishes only original summary prose
and short, verified quotations used for citation; no book text is reproduced here.
