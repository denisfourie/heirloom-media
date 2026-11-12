# heirloom-media

Public image host for Heirloom Amalgam social posts scheduled in Buffer.

Why this exists: Shopify's CDN re-processes every image it serves (WebP for some requests,
re-compressed progressive JPEG for others), and Instagram rejects some of those with
"There is an issue with the media included". raw.githubusercontent.com serves files byte-for-byte.

Rules:
- Every IMAGE for every channel (Instagram, Facebook, TikTok) is served from here. Never point a post at a Shopify-hosted image.
- Videos: posts use Shopify Files (served untouched as video/mp4). `video/` holds backup copies. Do not use raw links for video: raw serves mp4 as application/octet-stream.
- Save as baseline JPEG, sRGB, no ICC profile, quality 90, before adding here.
- Folders: `YYYY-MM/YYYY-MM-DD/` for new days; `library/` for reused images; `fixes/` for the watchdog; `video/` for reel backups.
- Use URLs of the form https://raw.githubusercontent.com/denisfourie/heirloom-media/main/<path>
- Never delete or rename a file that a scheduled post still uses.
