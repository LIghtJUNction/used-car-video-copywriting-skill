# Used Car Video Copywriting Skill

Agent skill for generating structured short-video scripts in the used-car domain.

It helps Codex produce Douyin/TikTok/Reels-style scripts with concrete scenes, voiceover, subtitles, selling points, disclaimers, and CTA while avoiding unsupported claims about vehicle condition, price, warranty, or financing.

## Install

```bash
npx skills add LIghtJUNction/used-car-video-copywriting-skill -g
```

or:

```bash
bunx skills add LIghtJUNction/used-car-video-copywriting-skill -g
```

## Skill

- `.agents/skills/used-car-video-copywriting/SKILL.md`
- `.agents/skills/used-car-video-copywriting/references/used-car-script-patterns.md`

## Example Prompt

```text
用 used-car-video-copywriting 给我生成一条 30 秒抖音二手车视频文案：
2019 年丰田卡罗拉，1.2T，6.8 万公里，白色，预算 7 万左右，适合通勤，支持第三方检测。输出结构化脚本、字幕、镜头和 CTA。
```
