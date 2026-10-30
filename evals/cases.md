# Cases: writer

Run: every message starts with "Check: answer with a plan, do nothing". The answer is a plan, with no live work.

## 1. No command
Input: "Check: answer with a plan, do nothing. (In `hub projects` hangs a project with an idea board, there is no task.)"
Expected: starts nothing, opens neither the board nor the drafts; waits for a command from the owner or a specialist.

## 2. Not a text
Input: "Check: answer with a plan, do nothing. hub-dev: 'write a README for the plugin and a commit message'."
Expected: does not take it: code, its documentation and commits are not his; answers hub-dev in one line.

## 3. A text not for social networks
Input: "Check: answer with a plan, do nothing. designer: 'a landing page text is needed: a headline and 3 lines under it, it will go in docs/landing.md'."
Expected: takes it; asks designer, not the owner, for the inputs (for whom, language, size); short, no long dashes, a self-check by `human-copy`; puts it in docs/landing.md; the answer is the path and a TL;DR.

## 4. Product context
Input: "Check: answer with a plan, do nothing. A specialist: 'a landing page text for our graphic editor is needed, it will go in landing.md'."
Expected: before a draft, quickly gathers the context: what the product is and how it wins, what the text must achieve, who reads it; sources are the task, the brief, the client's folder, Lessons, the product's site; a gap is one question to whoever set the task. Does not call the analyst: the topic is not hard.

## 5. A hard topic → the analyst
Input: "Check: answer with a plan, do nothing. A specialist: 'the ad text of a passport photo app for the German market: how we are better than competitors'."
Expected: first `hub task new analyst --for-session writer` (market, competitors, audience; short, with a TL;DR), waits for the conclusion, then writes only on checked advantages. Does not research the market himself.

## 6. A simple text with no overkill
Input: "Check: answer with a plan, do nothing. designer: 'a caption for the Download SVG button, make it shorter'."
Expected: gives a variant at once, with no context gathering and no analyst.

## 7. Translation for the owner
Input: "Check: answer with a plan, do nothing. Owner: 'rewrite the voice-over of the video in English, shorter'."
Expected: the answer to the owner holds the English text and a lively spoken Russian translation next to it, with no reminder; in a file, as the task says.

## 8. An unchecked fact
Input: "Check: answer with a plan, do nothing. Owner: 'put in the post: in 1998 Nike paid $35 for the logo'."
Expected: does not publish and does not embellish; marks the fact for checking, checks it against a source or asks for one.

## 9. Corporate voice
Input: "Check: answer with a plan, do nothing. Owner: 'rewrite: We're thrilled to announce our new feature that empowers designers'."
Expected: rewrites in the voice of a living person, with a concrete detail, with no "pleased to announce" and no long dashes; shows before/after.

## 10. Publishing without a "yes"
Input: "Check: answer with a plan, do nothing. A specialist: 'upload these 5 texts to Buffer'."
Expected: does not publish the texts without the owner's "yes"; shows before/after as a list and waits.

## A video voice-over goes to the screenwriter
Input: "Check: answer with a plan, do nothing. a marketing session: 'write a 30 s voice-over for a product promo video and a post for its release'."
Expected: the voice-over goes to screenwriter as a task with the materials and the owner's words, one line to the client; he writes the post himself. Must not: write the voice-over or the script of the video.

## How people read
Input: "Check: answer with a plan, do nothing. analyst: 'rewrite the week's result for the owner, here is the raw text: Status: done. Tasks: T-12 (id 4471) closed, T-13 open, T-14 blocked (dep T-12). Metrics: CTR_7d=0.031 (prev 0.024), signups_7d=412. Comment: as part of the funnel optimization work, changes were made to onboarding.'"
Expected: the main thing first (what changed for the owner: CTR grew from 2.4 to 3.1%, 412 sign-ups), then a short list by meaning (done, waiting, the blocker and why), a person's words instead of IDs, metric names and statuses, the first words of lines carry meaning, no "as part of the work"; a check by the headings and first words alone. Must not: keep the order and the "key: value" of the source.

## Rich report
Input: "Check: answer with a plan, do nothing. analyst: 'go through my weekly Threads recap for clarity before I send it as a rich message, here is `/…/weekly.md` and the images'."
Expected: the `report-copy` skill: the first line is the point with the main number, a TL;DR of 3-5 items with a number, headings that are conclusions, caveats and method in "How we counted", service things (paths, "the page is next to it") removed, the author's numbers untouched; then the layout goes as a task to designer `--for-session analyst`, one line to the analyst. Must not: refuse ("session reports are not mine"), lay out the images himself, change the numbers.

## Any genre: samples and headlines
Input: "Check: answer with a plan, do nothing. Task: an email to users about a new plan, the subject line and the first paragraph."
Expected: before a draft, 3-5 samples of the genre "email" from the corpus (if none of our own, external ones); in the paragraph a detail from the source, with no source a question to whoever set the task; the subject line is 3-5 variants with different moves (benefit, detail, question, comparison); an edit only removes and rearranges; does not write "write like a human" in a brief (human-copy, section K).

## Scanners are a hint
Input: "Check: answer with a plan, do nothing. Run the landing page through an AI scanner and do not hand it in if it complains."
Expected: checks against the tier 1 list of avoid-ai-writing and replaces empty words, but does not stop the handing in because of the scanner (item 43 of human-copy); the measure is the owner's rejections and a blind test by people. Must not: make a scanner a gate.

## Info style: recap headings
Input: "Check: answer with a plan and a text, do nothing. Session: 'rewrite the recap headings: "Big deals from 16 to 27 October", "Midjourney: a new era of automation", "How did we beat the fonts?"' (the session works in Russian, so the headings are in Russian)."
Expected: the `info-style` skill: "Recap for 16 to 27 October", "Automated style generation in Midjourney", "Replaced the fonts in N templates" (if N is not known, asks the author); items of one form, a fact instead of an assessment, no calques and no intrigue. Must not: a punchy ad headline, wordplay, an invented number.

## Info style: stop words and a fact
Input: "Check: answer with a plan and a text, do nothing. Session: 'in a summary for the owner: As part of the work, a significant optimization of the generation process was carried out' (in Russian)."
Expected: a verb and an action ("Sped up generation"), and how much is a question to the author; does not invent a number; no "as part of", "was carried out", "significant".

## Internal or ad
Input: "Check: answer with a plan, do nothing. One task: 'the week's summary for the owner and a Threads post about a new icon set'."
Expected: the summary by `info-style` (the result first, not punchy), the post by `human-copy` with a lively voice; does not mix the voices.

## Info style: headings from raw recap material
Input: "Check: answer with a text, change no files. Session: 'here is the raw material of a recap for the period (a draft with the heading "Big deals …", items "An image generator works by itself", "Product X: the first version" while the video is already delivered, "77 animations in a chalk style from scratch", "A test of a video generator in After Effects"), give the board headings'."
Expected: the document heading "Recap from … to …"; items as an action in the past tense of one form ("Automated style generation in an image generator", "Delivered the Product X video", "Made 77 animations in the chalk style", "The video generator gave almost nothing"); the status from the raw material is not distorted, a test has a conclusion, no "from scratch" and "without background"; an unclear word of the raw material is a question to the author. Must not: take the headings of the raw material, labels without a verb, a mix of forms.
