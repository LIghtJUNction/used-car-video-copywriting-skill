---
name: used-car-video-copywriting
description: Generate structured short-video scripts for used-car sales and used-car industry content, optionally using Douyin CLI competitor research. Use when Codex needs to create, rewrite, score, or adapt Douyin/TikTok/Reels-style video copy for second-hand cars, car dealers, inventory showcases, buyer education, trade-in stories, appraisal content, vehicle deal explanations, or competitor-video-informed scripts with fields such as hook, shots, voiceover, subtitles, selling points, risk disclaimers, and call to action.
---

# Used Car Video Copywriting

## Overview

Create structured short-video scripts for used-car content while preserving factual constraints and avoiding unsupported promises. Prefer concrete vehicle facts, buyer-use scenarios, visual shot planning, comment-driven objections, standard SRT subtitles, and compliance-safe sales language over generic hype. For commercial inquiry scripts, use a sharing/advisory tone instead of preachy or obvious advertising language.

## Workflow

1. Capture inputs: vehicle facts, audience, platform, tone, video length, target action, and forbidden claims.
2. If the task is for Douyin or China used-car content and competitor context would improve the result, use the optional Douyin CLI research workflow below.
3. If facts are incomplete, either ask for the missing high-risk fields or mark assumptions explicitly.
4. Select a script type: inventory showcase, buyer education, comparison, trade-in/appraisal, store trust, or after-sales reassurance.
5. Use `线师傅` as the fixed creator persona unless the user explicitly overrides it.
6. If the content is meant to match the `线师傅二手车` IP, read `references/xian-shifu-ip-profile.md` and apply the vertical positioning, product-driven style, and hard off-road/commercial vehicle language.
7. For China/Douyin used-car scripts, especially hard off-road, pickup, commercial vehicle, or dealer-reply content, read `references/real-data-patterns.md` and use its dataset-derived title,口播,评论, and CTA patterns.
8. Produce structured output with scenes, voiceover, subtitles, visual instructions, selling points, risk notes, and CTA.
9. If the user asks for subtitles, SRT, captions, 剪映/PR-ready output, or an extractable subtitle file, output standard SRT inside a Markdown fenced code block as described in `references/real-data-patterns.md`.
10. Run the quality checklist before finalizing: factual, specific, short-video paced, and not legally overclaiming.

## Optional Douyin CLI Research

If the user asks for Douyin-oriented scripts, competitor analysis,同行视频,爆款参考,账号调研, or current market style, use Douyin CLI when available. The companion skill can be installed with:

```bash
npx skills add LIghtJUNction/douyin -g
```

Use the installed `douyin-cli`/`douyin` skill first for exact command syntax and authentication requirements. Then search Douyin for relevant used-car competitors, accounts, or videos using queries such as:

- `二手车`
- `<brand/model> 二手车`
- `<city> 二手车`
- `二手车 避坑`
- `二手车 检测`
- `二手车 收车`

When using competitor videos:

- Extract reusable patterns: opening hook type, scene order, trust proof, buyer persona, CTA, comment prompts, and repeated objections.
- Do not copy creator wording, captions, account identity, private data, or unsupported claims.
- Summarize research as `douyin_research_notes` before generating the final script.
- If Douyin CLI is unavailable, unauthenticated, rate-limited, or network-blocked, say so briefly and continue from the provided facts and known patterns.

## Required Output

When generating a full script, return this structure unless the user asks for a different format:

- `title`: short working title.
- `positioning`: buyer persona, core pain point, and video intent.
- `facts_used`: list of concrete facts used from the prompt.
- `missing_facts`: important unknowns that affect trust, pricing, or legality.
- `douyin_research_notes`: optional notes from Douyin CLI competitor/video search, or `not_used` with reason.
- `hook_options`: 3 opening hooks, each under 18 Chinese characters when writing Chinese copy.
- `scene_script`: timecoded scenes with shot, action, voiceover, subtitle, and purpose.
- `srt_subtitles`: when requested, a Markdown fenced code block tagged `srt` that uses standard SRT numbering, `HH:MM:SS,mmm --> HH:MM:SS,mmm` timecodes, subtitle text, and one blank line between subtitle blocks.
- `selling_points`: 3-5 supported points tied to buyer needs.
- `risk_disclaimers`: wording that keeps the copy honest.
- `cta`: one action request, matched to the platform and sales funnel.
- `hashtags`: optional platform tags if useful.
- `version_notes`: what can be changed for a harder sell, softer sell, or educational angle.

## Style Rules

- Use specific, inspectable facts: year, model, mileage, powertrain, trim, ownership, maintenance, accident/flood/fire status, inspection result, price logic, and target buyer.
- Front-load the buyer's real decision conflict: price/year,手续/报废年限,落户/过户,两驱/四驱,汽油/柴油,维修/油耗,用途是否匹配.
- Do not invent certifications, accident-free claims, warranty terms, financing terms, or price advantages.
- Avoid empty slogans such as "车况精品", "闭眼入", "全网最低", "准新车" unless the prompt provides proof and the wording is still defensible.
- Convert technical details into buyer value: fuel cost, family use, city parking, long-distance comfort, resale stability, maintenance cost.
- Keep each shot visually executable; every sentence should imply something the camera can show.
- Prefer natural spoken Chinese for China used-car content; avoid translated English marketing tone.
- For commercial vehicles and pickups, treat policy/procedure facts as sales facts:年限,报废,手续,落户,过户,年审,高速,蓝牌/C照,车厢尺寸,座位数,载货场景.
- For bus, coach, van, and other commercial inquiry scripts, avoid lecturing openings such as `别一上来只问便宜不便宜` unless rewritten as a soft shared observation. Use `很多人先看价格，但真正影响后面能不能用的是...` style phrasing to reduce ad smell.
- When the goal is lead collection on Douyin/short-video platforms, keep the CTA singular and platform-safe: ask for budget, seats, use case, and city; avoid broad marketing words, exaggerated promises, repeated `私信我`, or aggressive conversion language that may trigger platform limiting.
- Default persona is `线师傅`: product-driven, vertical, practical, trust-oriented, focused on hard off-road vehicles, commercial vehicles, and pickups.
- Make the vehicle the protagonist. Do not turn `线师傅` scripts into comedy, plot skits, lifestyle vlogs, or generic car-influencer commentary.
- Treat competitor persona names as research labels only. Do not output `车商赋能金子`, `面包车老炮面包哥`, or `老实车贩子阿强` as the creator persona, self-introduction, account positioning, title, subtitle, or voiceover.
- Treat task-template phrases as instructions, not audience-facing copy. Do not output analysis labels, role prompts, fixed task wording, or prompt scaffolding such as "你是二手车行业短视频标题助手", "根据用户提供的口播文案", "只输出标题", "不要输出分析说明", or field names like "参考人设" unless the user explicitly asks for a prompt/template.
- Do not copy raw competitor captions, transcript wording, or comment text. Abstract the pattern, then rewrite from the supplied vehicle facts.

## Reference

- For detailed templates, script archetypes, scoring rubrics, field definitions, and dataset-derived industry language, read `references/used-car-script-patterns.md` before producing a complex script, batch variants, persona-specific copy, or quality review.
- For `线师傅二手车` IP-specific positioning, title formulas,口头禅, shooting flow, audience logic, and differentiation rules, read `references/xian-shifu-ip-profile.md`.
- For real raw-data-derived Douyin patterns from posts, subtitles, comments, audience objections, and Markdown-wrapped SRT subtitle output rules, read `references/real-data-patterns.md` before producing Douyin-facing hard off-road, pickup, commercial vehicle, subtitle, or comment-reply scripts.

## Quality Checklist

- The first 3 seconds state a buyer-relevant conflict, not a vague greeting.
- The opening sounds like practical sharing, not a scolding lesson or hard ad.
- The script can be filmed with real vehicle footage and simple dealership shots.
- Every major claim is traceable to the provided facts or marked as an assumption.
- Commercial/pickup scripts answer the likely comment questions: price/year,手续/报废年限,能否落户/过户,柴油/汽油,两驱/四驱,油耗/维修, and inspection/logistics boundaries when relevant.
- Requested subtitle output uses standard SRT syntax inside Markdown, with comma milliseconds and blank lines between blocks.
- The CTA is singular and concrete.
- Commercial inquiry CTAs collect only the minimum matching facts:预算,座位数,用途,城市.
- The script includes safety language for price, condition, financing, warranty, and inspection when those facts are uncertain.
