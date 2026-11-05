---
name: google-ads-research
description: >
  Research advertisers and creatives in the Google Ads Transparency Center
  with adextract. Use when the user asks for Google Ads research, YouTube ad
  research, Google advertiser lookup, domain-based ad research, or Google Ads
  Transparency Center analysis.
---

# Google Ads Research

## When to use

Use this skill for Google Ads Transparency Center research by brand, domain,
advertiser ID, platform, ad format, or date range.

## Tool workflow

1. Resolve the advertiser with `search_google_ads_advertisers` when the user gives only a brand name.
2. Search creatives with `search_google_ads` using `advertiser_id` or `domain`.
3. Filter deliberately with `region`, `platform`, `ad_format`, and `time_period`.
4. Fetch full creative data with `get_google_ad_details` for the most relevant ads.
5. Use `ad_reader` on returned media URLs or thumbnails before making creative claims.

## Research defaults

- Prefer `domain` when the user provides a website.
- Prefer `advertiser_id` after resolving official advertisers.
- Use `platform: youtube` for YouTube creative research.
- Use `ad_format: video`, `image`, or `text` when the user asks about a format.
- Paginate with `next_page_token` when the first result set is too thin.

## Output

Return the advertiser source, filters used, notable creative patterns, funnel
role, format mix, and 3-5 evidence-backed findings. Call out gaps caused by
missing media or details results.
