---
name: meta-ads-research
description: >
  Research Facebook and Instagram ads in the Meta Ad Library with adextract.
  Use when the user asks for Meta ads research, Facebook ads research,
  Instagram ads research, page-level ad analysis, or Meta Ad Library analysis.
---

# Meta Ads Research

## When to use

Use this skill for Meta Ad Library research by keyword, Facebook page, country,
platform, active status, media type, date range, or regulated ad category.

## Tool workflow

1. Resolve pages with `search_meta_pages` when the user gives a brand name.
2. Search ads with `search_meta_ads` using `page_id` for brand-specific work or `q` for category research.
3. Use `get_meta_page_info` when page identity, verification, followers, or transparency matters.
4. Use `get_meta_ad_details` with `ad_details_token` for EU/UK transparency details when available.
5. Use `ad_reader` on top image or video assets before summarizing creative strategy.

## Research defaults

- Use `active_status: active` for current market research unless the user asks for history.
- Use `sort_by: impressions_high_to_low` for likely high-reach creative review.
- Use `platforms: facebook,instagram` unless the user names a specific Meta surface.
- Use `media_type` to separate video, image, and meme analysis.
- Keep country filters explicit; `ALL` is broad and can mix markets.

## Output

Return page identity, filters used, current message themes, platform/format
mix, offer and CTA patterns, emotional strategy, and 3-5 evidence-backed
creative observations.
