# Real Data Patterns

Use this reference when writing Douyin-facing used-car scripts, especially for `线师傅二手车`, hard off-road vehicles, pickups, commercial vehicles, light trucks, vans, subtitles, and comment-reply content.

These patterns were distilled from local raw Douyin data under `data/raw/douyin/` in the used-car dataset project, plus normalized feature files under `data/working/features/`. The useful sample included post/caption signals, subtitle/口播 segments, and audience comment signals. Treat all examples as pattern evidence, not wording to copy.

## Data Signals To Preserve

Prefer these real audience and creator signals over generic car-review language:

- Buyer intent is concrete and transactional: what year, what price, where, can it transfer, can it settle locally, diesel or gasoline, two-wheel or four-wheel drive, can finance, annual inspection, scrappage years, holiday highway policy.
- Commercial-vehicle buyers care about downtime and paperwork as much as specs:手续,年限,报废,蓝牌/C照,座位数,车厢/货箱长度,载货能力,油耗,维修成本.
- Pickup/light-truck buyers often compare legal/use constraints before comfort:报废年限,落户/过户,年审,能不能进城,柴油审车,汽油油耗,两驱/四驱.
- Practical buyers respond to scenario-first framing:工地备用车,拉货创业,房车底盘,工程维修,低预算通勤,退休后玩车,一车多用.
- Trust comes from showing proof and limits, not declaring perfection:公里数,磨损,发动机舱,底盘,手续类型,过户条件,检测报告,一手/单位/办公用车来源 when provided.

## Title And Hook Patterns

Build titles from factual anchors. Keep them searchable and concrete.

Strong data-derived formulas:

- `价格 + 车型 + 程序/手续优势`: `七万多 + 经典全顺皮卡 + 无报废年限`.
- `车型 + 关键取舍`: `五十铃皮卡，汽油和柴油到底怎么选`.
- `老车风险 + 车况证明`: `经典全顺价格乱，先看车况再谈价`.
- `用途 + 车型`: `创业拉货，几万预算看柴油皮卡`.
- `稀缺规格 + 可见事实`: `低公里依维柯，后双轮更稳`.
- `同款差异 + 为什么值钱`: `同样是货车，手续不同年限差很多`.

Avoid title patterns that the raw data makes risky:

- Claiming `无报废`, `30年`, `全车螺丝未动`, `一手`, `实表`, `无越野史`, `原版原漆`, `全国发货`, or `支持三方检测` without user-provided proof.
- Leading with `精品`, `极品`, `闭眼入`, `捡漏` when no visible proof follows.
- Copying competitor account names or raw captions as final output.

## Voiceover Structure

Use a practical, spoken, front-loaded structure:

1. Open with the vehicle's decision conflict, not a greeting.
2. Name the buyer or use scenario.
3. Show the fact that changes the decision:手续,年限,公里数,发动机,车厢尺寸,座位数,磨损,底盘,来源, or price band.
4. Explain one tradeoff honestly.
5. Close with a narrow CTA tied to inquiry, inspection, or logistics.

Good spoken openings:

- `买这种老全顺，别先问便宜不便宜，先看车况和手续。`
- `工地备用车，预算不高，重点不是配置，是年限和维修成本。`
- `这台皮卡值钱的地方，不是外观，是这套手续。`
- `汽油和柴油怎么选，先看你是家用还是天天拉货。`
- `这类车适合谁，不适合谁，先说清楚。`

## Standard SRT Output In Markdown

When the user asks for subtitles, SRT, captions, 剪映/PR-ready output, or "输出为 md 方便提取", output a Markdown section containing only one fenced `srt` code block for the subtitle file.

Use standard SRT syntax:

- Number every subtitle block from `1`.
- Use timecodes in `HH:MM:SS,mmm --> HH:MM:SS,mmm` format.
- Use a comma before milliseconds, not a period.
- Put subtitle text after the timecode line.
- Separate subtitle blocks with one blank line.
- Encode final file content as UTF-8 if writing a file.

Format:

```srt
1
00:00:00,000 --> 00:00:03,000
买这种老全顺，先看车况和手续。

2
00:00:03,000 --> 00:00:06,500
预算不高，重点不是配置。
```

For Markdown deliverables, wrap the code block under a clear heading such as `## SRT 字幕`. Do not add explanations inside the `srt` block. If also returning a script, keep the script outside the code block and keep `srt_subtitles` easy to copy.

## Comment-Driven Objection Map

When generating scripts or comment replies, proactively cover likely comments:

- `多少钱/几年的/在哪里`: include price band, year, region, and `以当天报价/实车为准` if exact data is missing.
- `能落户/过户吗`: state only provided policy facts; otherwise use `需要按当地政策和车管所结果确认`.
- `有没有四驱/柴油/汽油`: answer from facts; if unknown, put it in `missing_facts`.
- `年审/报废年限`: treat as a core risk point for pickup, truck, van, and commercial scripts.
- `油耗/维修贵不贵`: compare use-case tradeoffs rather than promising exact cost.
- `能分期吗`: mention financing only if provided; otherwise use `金融方案以实际审核为准`.
- `适合家用吗`: for工具车, be honest about comfort, image, parking, city restrictions, and family acceptance.

## Commercial Vehicle Rules

For vans, pickups, light trucks,依维柯,全顺,五十铃,金杯,清障车,工程车:

- Lead with use value:拉货,工程,创业,房车底盘,备用车,单位办公,低成本生产工具.
- Mention paperwork and limits before features when relevant.
- Translate specs into workflow value: `5.99米蓝牌` -> license/access convenience if true; `后双轮` -> stability/load confidence; `九座` -> crew transport; `货箱长度` -> loading utility.
- Use `维修便宜比配置重要` only as a principle, then attach it to an actual powertrain or parts availability fact.
- Keep comfort claims modest; commercial buyers in the data often challenge image, policy, fuel, and inspection more than seat features.

## Hard Off-Road And Pickup Rules

For帕拉丁,帕杰罗,牧马人,普拉多,DMAX,庆铃,五十铃,日产D22,拓陆者:

- Treat `无越野史` as a high-value trust anchor only with proof.
- Separate hobby use from production use:越野/露营/退休玩车 is not the same pitch as工地/拉货/创业.
- Mention底盘/四驱/发动机/磨损 only when visible or provided.
- Explain old-car tradeoffs:油耗,年限,审车,维修,配件,舒适性, city policy.

## Safe CTA Patterns

Prefer one concrete CTA:

- `想看检测报告，私信车型。`
- `要落户/过户政策，先发你所在城市。`
- `想找同类车，发预算和用途。`
- `要看底盘和手续细节，私信发实拍。`
- `到店试车前，先确认年份、手续和预算。`

Avoid broad CTAs like "喜欢的点关注" when the task is sales, inquiry, or trust building.

## Generation Guardrails

- Preserve vehicle facts over stylish phrasing.
- Mark unknown policy and paperwork details as missing instead of guessing.
- Use comment objections to choose scenes, not to publish private user data.
- Write subtitles shorter than voiceover and keep them searchable:车型,预算,用途,手续,年限,风险.
- For batch scripts, vary by decision problem:价格预算,手续年限,车况证明,用途场景,买家顾虑, not only by wording.
