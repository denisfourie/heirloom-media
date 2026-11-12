# heirloom-media

Public image host for Heirloom Amalgam social posts scheduled in Buffer.

Why this exists: Shopify's CDN re-processes every image it serves (WebP for some requests,
re-compressed progressive JPEG for others), and Instagram rejects some of those with
"There is an issue with the media included". raw.githubusercontent.com serves files byte-for-byte.

Rules:
- Images only (videos stay on Shopify Files, which serves them untouched).
- Save as baseline JPEG, sRGB, no ICC profile, quality 90, before adding here.
- Folders: `YYYY-MM/YYYY-MM-DD/` for new days; `library/` for reused images.
- Use URLs of the form https://raw.githubusercontent.com/denisfourie/heirloom-media/main/<path>
- Never delete or rename a file that a scheduled post still uses.
