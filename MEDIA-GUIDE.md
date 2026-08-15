# Where every image and video goes

All media lives in `images/` and `videos/`, referenced by plain `<img src="images/...">` and
`<video src="videos/...">` tags in `index.html`. To swap something out, replace the file
(keep the same filename) — or open `index.html`, search for the filename, and point it at a
new file instead.

Every insertion point also has an HTML comment directly above it, e.g. `<!-- File: images/logo-3.png -->`,
so you can just search the file for the section name (Ctrl+F "Logo Design") to jump straight there.

## Hero
| File | Used for |
|---|---|
| `images/hero-photo.png` | Bust photo at the top of the page |

## Bio
| File | Used for |
|---|---|
| `videos/bio-intro.mp4` | Short intro clip under the bio heading |

## Work
| File | Used for |
|---|---|
| `images/work-1.png` – `images/work-6.png` | Project spotlight gallery |

## Brand Identity
| File | Used for |
|---|---|
| `images/brand-identity-1.png` | Piece 1 |
| `images/brand-identity-2.png` | Piece 2 |

## Web Design
| File | Used for |
|---|---|
| `images/web-design-1.png` | Piece 1 |

## Logo Design
| File | Used for |
|---|---|
| `images/logo-1.png` – `images/logo-7.png` | Logo marks |
| `videos/logo-video-1.mp4` – `videos/logo-video-4.mp4` | Logo animation/presentation clips |

## Video Content
| File | Used for |
|---|---|
| `videos/reel-1.mp4` – `videos/reel-14.mp4` | Short-form video: reels, promos, behind-the-scenes |

## Social Media Content
| File | Used for |
|---|---|
| `images/social-1.png` – `images/social-5.png` | Post graphics |
| `videos/social-video-1.mp4` – `videos/social-video-13.mp4` | Video content |

## Closing banner
| File | Used for |
|---|---|
| `images/closing-banner.png` | Final image before the contact section |

---

## To add more, or rearrange

Every tile in the Work section sits inside a `<div class="media-tile">`. To add a new one,
copy an existing tile and change the filename:

```html
<div class="media-tile reveal-scale">
  <img src="images/your-new-file.png" alt="Description" loading="lazy">
</div>
```

For video, use:

```html
<div class="media-tile reveal-scale">
  <video src="videos/your-new-file.mp4" controls muted playsinline preload="metadata"></video>
</div>
```

The grid (`.media-masonry`) auto-arranges tiles by column, so order in the HTML is left-to-right,
top-to-bottom — reordering the `<div class="media-tile">` blocks reorders the gallery.

## Notes

- Two images from the original Canva export were left out: the two blank/empty iPhone mockup
  frame graphics with nothing on the screen — they didn't add anything on their own once
  separated from the original Canva canvas.
- Videos are set to `controls muted playsinline` (click to play) rather than autoplay, since
  autoplaying 30+ videos at once would slow the page down badly. The bio intro clip at the top
  is the only one that autoplays, since it's just the one.
- Every video in this repo has been re-muxed with `faststart` (the moov atom moved to the front
  of the file) and decode-verified frame by frame with ffmpeg before being included — this is
  the most common reason an exported video plays fine on your phone but shows a blank box in a
  browser, so it's been fixed at the source rather than left for you to debug.
