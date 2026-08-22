# claritylane-assets

Public asset host for the social-media automation in
[`claritylane-socialmedia`](https://github.com/santoshtanugula/claritylane-socialmedia).

This repo exists only so Buffer can fetch files by URL. Buffer has no upload mutation — an
Instagram image or a LinkedIn document carousel has to already be hosted somewhere public — and
that requirement was the last thing keeping the main repo public. Splitting the assets out lets
everything else (drafts, metrics, the ledger, the authoring prompts) go private.

| Folder | What's in it | Consumed by |
|---|---|---|
| `instagram/` | Rendered Instagram cards | `IMAGE_BASE_URL` |
| `carousels/` | LinkedIn carousel PDFs + cover PNGs | `CAROUSEL_BASE_URL` |
| `architecture.jpg` | System diagram | docs |

Base URLs, set as Actions **variables** on the main repo:

```
IMAGE_BASE_URL    = https://raw.githubusercontent.com/santoshtanugula/claritylane-assets/refs/heads/main/instagram
CAROUSEL_BASE_URL = https://raw.githubusercontent.com/santoshtanugula/claritylane-assets/refs/heads/main/carousels
```

**Keep this repo public.** Making it private returns 404 to Buffer, which posts with a silently
missing asset rather than failing.
