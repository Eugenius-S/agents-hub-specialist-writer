---
name: report-copy
description: The text of a report to the owner that goes out as one Telegram rich message and an .md file in the hub chat (`hub send-rich`, an optional hub extension, not a core command): the point in the first line, headings that are conclusions, short blocks, numbers with a comparison, caveats in a collapsible block. Use when a session asks to rewrite or "go through for clarity" a report, a recap, a review for the owner.
---

# The text of a rich report

A report is read on a phone, on the go: a person must grasp the main thing from the first line and the headings. You write the words and the order of thought; images, collages, tables and collapsible blocks are placed by the designer (the `rich-report` skill). When the text is ready, you hand the layout to the designer as a task `--for-session <author>` (if there are no images and tables, give the author the full path to the `.md` at once). The one whose report it is sends it.

## Rules
1. **The first line is the point**, one sentence: what happened, the main number, what is needed from the owner. Above it a short `#` heading (what and for what period). Not "Recap for the week of 17-23 October" but "One post took off: a napkin sketch, 210 likes; views are 18 times lower".
2. **TL;DR is 3-5 items**, one thought per item, a number or a name in each; it does not repeat the first line. Not a paragraph of six lines.
3. **A section heading is a conclusion, not a topic**: "Comments have been arguing with the post for a second week", not "Insights from the comments".
4. **A paragraph is up to three phone lines** (~250 characters), one thought. The first words of a paragraph and an item carry the meaning: people read by them, skimming.
5. **Numbers with a comparison next to them**: "596 likes, a week earlier 1,279". Thousands with a space. "N times" and percentages are for the main thing, not for every line.
6. **Caveats go down.** "By Buffer in the morning", "counted over 7 posts", the method, the sources, "what is unknown" go in a footnote `[^1]` or in a section "How we counted" at the end (the designer will collapse it). The main text holds only what changes the conclusion: such a "we do not know" is one line below, in plain sight. A threshold or a term without which a number is not clear ("took off = 200+ likes") goes in brackets at first mention.
7. **A quote** is a line with `>`, right under it the meaning in the owner's language and the likes. Do not leave a quote in a foreign language without a translation.
8. **No service things**: paths and file names, scripts, session names, ids, "the page is next to it", "by the project rule", links to internal reviews and selections ("the review of 20 October", "added to best-posts") do not go into the report; if you need the conclusion of a review, write the conclusion itself.
9. **What is needed from the owner** goes in the last line "Needed from you: …". If nothing is needed, do not write it.
10. Project terms the owner knows (the names of sections, a label for a post that worked) you keep; internal abbreviations and metric keys (`CTR_7d`) go in words.

## What you do not touch
The author's numbers, facts, conclusions. If in doubt about a fact or a number, ask the author, do not fix it yourself. What is superfluous by meaning (a repeat, a detail that does not change the conclusion) you remove or move to "How we counted".

## Check
- Read only the headings and the first line: is it clear what happened and what is needed from the owner.
- No paragraph longer than three phone lines and no TL;DR item without a number or a name.
- No service things (rule 8).
- Words and headings by `info-style`: straight in Russian, facts instead of assessments, no stop words, calques and ad voice.
