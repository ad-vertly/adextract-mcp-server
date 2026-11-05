---
name: tiktok-ads-research
description: >
  Research short-form creative strategy in TikTok Ads Library with adextract.
  Use when the user asks for TikTok ads research, TikTok creative analysis,
  UGC-style ad research, short-form video hooks, or TikTok competitor ads.
---

# TikTok Ads Research

## When to use

Use this skill for TikTok Ads Library research where hooks, creator style,
short-form video structure, trend fit, and direct response patterns matter.

## Tool workflow

1. Search advertisers with `search_tiktok_advertisers` when advertiser identity is unclear.
2. Search creatives with `search_tiktok_ads` using the brand, competitor, product, or category query.
3. Use `get_tiktok_ad_details` for targeting, audience size, and creative details on promising ads.
4. Use `ad_reader` on thumbnails or media URLs before describing visual strategy.

## Research defaults

- Prioritize hook, opening frame, creator style, offer, and CTA.
- Treat signed TikTok media URLs as fragile; use thumbnails when media URLs expire.
- Compare multiple ads before calling something a repeatable pattern.
- Separate organic-looking UGC from polished brand creative.

## Output

Return hook patterns, creator or production style, offer framing, emotional
driver, audience assumptions, CTA patterns, and 3-5 concrete creative tests.
