---
name: used-car-video-copywriting
description: Generate structured short-video scripts for used-car sales and used-car industry content. Use when Codex needs to create, rewrite, score, or adapt Douyin/TikTok/Reels-style video copy for second-hand cars, car dealers, inventory showcases, buyer education, trade-in stories, appraisal content, or vehicle deal explanations with fields such as hook, shots, voiceover, subtitles, selling points, risk disclaimers, and call to action.
---

# Used Car Video Copywriting

## Overview

Create structured short-video scripts for used-car content while preserving factual constraints and avoiding unsupported promises. Prefer concrete vehicle facts, buyer-use scenarios, visual shot planning, and compliance-safe sales language over generic hype.

## Workflow

1. Capture inputs: vehicle facts, audience, platform, tone, video length, target action, and forbidden claims.
2. If facts are incomplete, either ask for the missing high-risk fields or mark assumptions explicitly.
3. Select a script type: inventory showcase, buyer education, comparison, trade-in/appraisal, store trust, or after-sales reassurance.
4. Produce structured output with scenes, voiceover, subtitles, visual instructions, selling points, risk notes, and CTA.
5. Run the quality checklist before finalizing: factual, specific, short-video paced, and not legally overclaiming.

## Required Output

When generating a full script, return this structure unless the user asks for a different format:

- `title`: short working title.
- `positioning`: buyer persona, core pain point, and video intent.
- `facts_used`: list of concrete facts used from the prompt.
- `missing_facts`: important unknowns that affect trust, pricing, or legality.
- `hook_options`: 3 opening hooks, each under 18 Chinese characters when writing Chinese copy.
- `scene_script`: timecoded scenes with shot, action, voiceover, subtitle, and purpose.
- `selling_points`: 3-5 supported points tied to buyer needs.
- `risk_disclaimers`: wording that keeps the copy honest.
- `cta`: one action request, matched to the platform and sales funnel.
- `hashtags`: optional platform tags if useful.
- `version_notes`: what can be changed for a harder sell, softer sell, or educational angle.

## Style Rules

- Use specific, inspectable facts: year, model, mileage, powertrain, trim, ownership, maintenance, accident/flood/fire status, inspection result, price logic, and target buyer.
- Do not invent certifications, accident-free claims, warranty terms, financing terms, or price advantages.
- Avoid empty slogans such as "车况精品", "闭眼入", "全网最低", "准新车" unless the prompt provides proof and the wording is still defensible.
- Convert technical details into buyer value: fuel cost, family use, city parking, long-distance comfort, resale stability, maintenance cost.
- Keep each shot visually executable; every sentence should imply something the camera can show.
- Prefer natural spoken Chinese for China used-car content; avoid translated English marketing tone.

## Reference

For detailed templates, script archetypes, scoring rubrics, and field definitions, read `references/used-car-script-patterns.md` before producing a complex script, batch variants, or quality review.

## Quality Checklist

- The first 3 seconds state a buyer-relevant conflict, not a vague greeting.
- The script can be filmed with real vehicle footage and simple dealership shots.
- Every major claim is traceable to the provided facts or marked as an assumption.
- The CTA is singular and concrete.
- The script includes safety language for price, condition, financing, warranty, and inspection when those facts are uncertain.
