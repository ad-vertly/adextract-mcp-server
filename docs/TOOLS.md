# Tools, Prompts, and Resources

## Response shape

Search tools return a consistent envelope:

```json
{
  "engine": "meta_ad_library",
  "search_parameters": {},
  "search_information": { "total_results": 482 },
  "items": [
    {
      "id": "...",
      "advertiser": "Nike",
      "headline": "...",
      "body": "...",
      "platforms": ["FACEBOOK", "INSTAGRAM"],
      "is_active": true,
      "media": [{ "type": "image", "url": "..." }],
      "raw": {}
    }
  ],
  "pagination": { "next_page_token": "..." }
}
```

Use `next_page_token` from the response to fetch the next page.

---

## Tool catalog

### Meta Ad Library

| Tool | Description |
|------|-------------|
| `search_meta_ads` | Search Facebook/Instagram ads by keyword, page ID, country, ad type, media, dates |
| `search_meta_pages` | Find page IDs and location IDs for targeted searches |
| `get_meta_page_info` | Followers, verification, transparency, spend |
| `get_meta_ad_details` | EU/UK transparency details (`ad_details_token` or `ad_archive_id`) |

### Google Ads Transparency Center

| Tool | Description |
|------|-------------|
| `search_google_ads` | Search creatives by `advertiser_id` or `domain`, region, time period |
| `search_google_ads_advertisers` | Discover advertisers and domains |
| `get_google_ad_details` | Full creative variations (`advertiser_id` + `creative_id`) |
| `get_google_ads_advertiser_info` | Advertiser details from Google Search ad tokens |

### LinkedIn

| Tool | Description |
|------|-------------|
| `search_linkedin_ads` | Keyword, advertiser name, country, date range |

### TikTok

| Tool | Description |
|------|-------------|
| `search_tiktok_ads` | Keyword, `advertiser_token`, or `advertiser_id` + `q` |
| `search_tiktok_advertisers` | Advertiser discovery by keyword |
| `get_tiktok_ad_details` | Targeting, audience size, creative details by `ad_id` |

### Creative analysis

| Tool | Description |
|------|-------------|
| `ad_reader` | Structured JSON: format, audience, Plutchik/VAD emotion, archetypes, industry/brand |

Pass a media URL from search results or any public image/video URL.

---

## MCP prompts

| Prompt | Use case |
|--------|----------|
| `adextract_top_ads_for_brand` | Top ads across platforms for one brand |
| `adextract_competitor_benchmark` | Compare two brands' creatives |
| `adextract_channel_strategy` | Infer channel mix and strategy |
| `adextract_analyze_ad_url` | Deep-dive one creative URL |
| `adextract_schedule_watchlist` | Playbook for recurring monitoring |

---

## MCP resources

| URI | Content |
|-----|---------|
| `adextract://skill/main` | Agent skill instructions |
| `adextract://prompts/pack` | Prompt pack reference |
| `adextract://skill/routines` | Scheduling / watchlist guidance |
