---
name: adextract
description: >
  Ad intelligence skill for competitor research, creative benchmarking,
  emotional analysis, and cross-platform ad strategy synthesis across Meta,
  TikTok, Google Ads Transparency Center, and LinkedIn.
---

# adextract

Use this skill when users ask to:
- find competitor ads
- analyze top-performing creatives
- compare brand messaging across platforms
- explain emotional strategy from ad creatives
- infer channel strategy from what is currently running

## Workflow

1. Search first, analyze second.
2. Run searches in parallel when covering multiple platforms.
3. Use `ad_reader` on top creatives (image/video URL or thumbnail).
4. Synthesize cross-platform strategy (format, emotion, funnel role).
5. If any tool call fails, ask the user to refresh/retry once, then continue.

## Key tools

- `search_meta_ads`, `search_meta_pages`, `get_meta_page_info`, `get_meta_ad_details`
- `search_google_ads`, `search_google_ads_advertisers`, `get_google_ad_details`
- `search_linkedin_ads`
- `search_tiktok_ads`, `search_tiktok_advertisers`, `get_tiktok_ad_details`
- `ad_reader`

## Platform skills (MCP)

For single-library research, read the platform skill resource or use its MCP prompt:

- Google: `adextract://skill/google-ads-research`
- Meta: `adextract://skill/meta-ads-research`
- LinkedIn: `adextract://skill/linkedin-ads-research`
- TikTok: `adextract://skill/tiktok-ads-research`

Catalog: `adextract://skills`

## Gotchas

- TikTok signed media URLs expire quickly; use thumbnails when needed.
- Google often requires `get_google_ad_details` to retrieve actual creative assets.
- Meta can return large payloads; focus analysis on the top results first.
