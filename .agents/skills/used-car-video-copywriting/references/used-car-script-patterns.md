# Used-Car Script Patterns

## Input Schema

Use these fields when asking for facts or normalizing a prompt:

- `vehicle`: brand, model, year, trim, powertrain, color, mileage, license city, emission standard.
- `condition`: accident, flood, fire, repaint, structural repair, tire/brake/battery state, inspection notes.
- `ownership`: number of owners, private/dealer source, maintenance records, transfer history.
- `price`: asking price, market reference, negotiability, included fees, financing constraints.
- `audience`: first car, family user, commuter, business owner, young driver, budget buyer, upgrade buyer.
- `platform`: Douyin, Kuaishou, Xiaohongshu, TikTok, Reels, YouTube Shorts.
- `goal`: inquiry, store visit, test drive, private message, lead form, education, trust building.
- `constraints`: forbidden claims, required disclaimers, region, language, tone, duration.
- `competitor_research`: Douyin CLI search terms, account/video references, observed hooks, repeated objections, and constraints from同行内容.

## Douyin Competitor Research

Use Douyin CLI research when current platform context matters. The goal is not to imitate a specific creator; it is to infer what the market is training viewers to expect.

Recommended search angles:

- Broad category: `二手车`, `二手车避坑`, `二手车检测`, `二手车收车`.
- Vehicle-specific: `<brand> <model> 二手车`, `<price_band> 二手车推荐`.
- Audience-specific: `新手买二手车`, `家用二手车`, `通勤二手车`, `年轻人第一台车`.
- Trust-specific: `二手车检测报告`, `二手车事故车`, `二手车整备`.
- Dealer positioning: `<city> 二手车`, `二手车商日常`, `二手车交车`.

Observation schema:

- `query`: search keyword.
- `source_count`: number of videos/accounts inspected.
- `common_hooks`: recurring opening patterns.
- `visual_proofs`: what creators show on camera to build trust.
- `buyer_objections`: repeated concerns in title/caption/comments if available.
- `cta_patterns`: private message, comment keyword, store visit, test drive, inspection report.
- `risk_patterns`: overclaims, exaggerated pricing, unsupported condition language to avoid.

Convert research into scripts by:

- Keeping the strongest hook structure but replacing wording and facts.
- Turning common objections into scene purposes.
- Using observed visual proof types only when the seller can actually film them.
- Making the final CTA fit the user's funnel, not the competitor's funnel.

## Script Archetypes

### Inventory Showcase

Use when the user wants to sell a specific car.

Structure:

1. Hook with price/use-case tension.
2. Show exterior and key identifiers.
3. Show interior wear and feature proof.
4. Explain condition with evidence, not adjectives.
5. Explain who should buy it.
6. Close with inspection/test-drive CTA.

### Buyer Education

Use when the user wants evergreen content.

Structure:

1. Start with a common buyer mistake.
2. Explain the cost/risk.
3. Show what to inspect.
4. Give a practical rule.
5. Invite viewers to send listings or ask questions.

### Comparison

Use when comparing models, trims, or budgets.

Structure:

1. Name the decision conflict.
2. Compare 3 buyer-relevant dimensions.
3. State who should choose each option.
4. Avoid declaring one universally better.

### Appraisal Or Trade-In

Use when explaining valuation or collecting acquisition leads.

Structure:

1. Hook with "why this car is worth/not worth more".
2. Show valuation factors: year, mileage, condition, market demand.
3. Explain deductions without insulting the owner.
4. CTA: send vehicle facts for estimate.

### Dealer Trust

Use when building credibility for a store or operator.

Structure:

1. Show process, not promises.
2. Demonstrate inspection, paperwork, handover, after-sales boundaries.
3. Mention what the store refuses to sell.
4. CTA: visit, reserve, or ask for inspection report.

## Scene Format

For full scripts, use this scene row format:

```text
00:00-00:03
Shot: Close-up of dashboard start-up / exterior walk-in / price card.
Action: What the creator does on camera.
Voiceover: Spoken line.
Subtitle: Short on-screen text.
Purpose: Hook / proof / transition / CTA.
```

## Hook Patterns

Good hooks:

- "10万预算，别只盯新车"
- "这台车适合谁，不适合谁"
- "公里数低，不等于车况好"
- "买二手车先看这三个位置"
- "同价位，为什么选这台"

Bad hooks:

- "家人们今天来了一台精品车"
- "全网最低价，错过没有"
- "闭眼入，放心冲"
- "准新车，原版原漆" without proof

## Claim Safety

Do:

- Say "以检测报告为准" when condition is central.
- Say "价格以门店当天报价为准" when quoting price.
- Say "支持第三方检测" if actually supported.
- Say "适合预算有限但想要空间/省油/配置的人" when matching buyer needs.

Do not:

- Promise accident-free, flood-free, warranty, financing approval, or lowest price without evidence.
- Hide uncertainties behind vague adjectives.
- Overstate future resale value.
- Present opinion as verified history.

## Output Variants

When asked for multiple versions, vary by strategy instead of only changing wording:

- `hard_sell`: faster rhythm, stronger price/use-case conflict, still fact-bound.
- `soft_trust`: calmer explanation, more inspection and suitability language.
- `educational`: less direct selling, more buyer decision guidance.
- `story`: owner/use-case narrative, then vehicle proof.
- `dealer_process`: focus on acquisition, inspection, preparation, paperwork.

## Scoring Rubric

Score generated scripts from 1-5 on:

- `specificity`: uses concrete vehicle facts rather than empty adjectives.
- `filmability`: each scene can be shot with normal dealer footage.
- `buyer_fit`: connects features to a clear buyer persona.
- `trust`: makes condition and price claims safely.
- `pace`: short-video rhythm is tight and front-loaded.

If any score is below 3, revise before final output.
