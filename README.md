# Used Car Video Copywriting Skill

Agent skill for generating structured short-video scripts in the used-car domain.

It helps Codex produce Douyin/TikTok/Reels-style scripts with concrete scenes, voiceover, subtitles, selling points, disclaimers, and CTA while avoiding unsupported claims about vehicle condition, price, warranty, or financing.

The skill uses `线师傅` as the fixed creator persona and includes an IP profile for product-driven hard off-road, commercial vehicle, and pickup content. It includes dataset-derived二手车行业黑话 such as `先建立信任再卖车`, `教学感`, `拆解式`, `工具属性优先`, `无越野史`, `量大管饱`, and explicit guards against leaking task-template phrases or competitor persona names into final scripts.

It also includes a real-data pattern reference distilled from local Douyin raw data: post titles/descriptions, ASR subtitle segments, comment objections, and audience intent signals. This improves commercial-vehicle/pickup scripts around price/year questions,手续/报废年限,落户/过户,柴油/汽油,两驱/四驱,维修/油耗, safer CTAs, and Markdown-wrapped standard SRT output for subtitles.

For二手大巴/客车/通勤车 scripts, the skill now favors分享式口播 over preachy hard-sell wording: lead with用途匹配,预算,座位数,城市, then use one platform-safe CTA such as `发预算+座位数+城市`.

## Install

Install this skill:

```bash
npx skills add LIghtJUNction/used-car-video-copywriting-skill -g
```

or:

```bash
bunx skills add LIghtJUNction/used-car-video-copywriting-skill -g
```

Optional companion skill for Douyin CLI research:

```bash
npx skills add LIghtJUNction/douyin -g
```

With the Douyin skill installed, an agent can use Douyin CLI to search同行视频、竞品账号、二手车爆款内容 and turn the observed hook/scene/CTA patterns into original structured scripts.

## Skill

- `.agents/skills/used-car-video-copywriting/SKILL.md`
- `.agents/skills/used-car-video-copywriting/references/used-car-script-patterns.md`
- `.agents/skills/used-car-video-copywriting/references/real-data-patterns.md`
- `.agents/skills/used-car-video-copywriting/references/xian-shifu-ip-profile.md`

## Example Prompt

```text
用 used-car-video-copywriting 给我生成一条 30 秒抖音二手车视频文案：
2019 年丰田卡罗拉，1.2T，6.8 万公里，白色，预算 7 万左右，适合通勤，支持第三方检测。输出结构化脚本、字幕、镜头和 CTA。
```

```text
先用 Douyin CLI 搜索二手车同行视频，参考近期二手车检测/避坑类内容的开头、镜头和 CTA，再给我生成一条原创的 45 秒结构化文案。
```
