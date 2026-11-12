# heirloom-media

Public host for ALL Heirloom Amalgam social media (photos and reels) scheduled in Buffer,
served through GitHub Pages (switched on 12 Nov 2026).

Why this exists: Shopify's CDN re-processes every image it serves (WebP for some requests,
re-compressed progressive JPEG for others), and Instagram rejects some of those with
"There is an issue with the media included". GitHub Pages serves files byte-for-byte with the
correct type (image/jpeg, video/mp4).

Rules:
- Every photo and every reel, on every channel (Instagram, Facebook, TikTok), is served from here.
- Use URLs of the form https://denisfourie.github.io/heirloom-media/<path>
- Never use Shopify for social media. Never use raw.githubusercontent.com links (raw labels mp4 as a generic download).
- Photos: baseline JPEG, sRGB, no ICC profile, quality 90. Reels: H.264, yuv420p, constant frame rate, with an audio track.
- Folders: `YYYY-MM/YYYY-MM-DD/` for new days; `library/` for reused media; `video/` for reels; `fixes/` for the watchdog.
- Pages takes about 1 to 2 minutes to publish after a push. Check the link returns 200 before scheduling.
- Clean-up: once a day the watchdog removes media that has been posted, is not used by any scheduled, draft or failed post,
  was not posted in the last 7 days, and has been here more than 7 days. Git history keeps a copy, so anything removed can be restored.
- Never delete or rename a file that a scheduled post still uses.
