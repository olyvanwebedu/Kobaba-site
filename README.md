# KOBABA Jornsen — Official Site

Single-page static site. No build step — `index.html` references everything
by relative path inside `/assets`, so it works the same on your PC, on
GitHub Pages, and on `kobaba.com`.

## Why this matters
The first version of this rebuild linked directly to images hosted on the
old Lovable preview (`kobaba-impact-hub.lovable.app`). That host blocks or
breaks those links when loaded from any other domain — which is exactly
what would have happened again on `kobaba.com`. This version removes that
dependency entirely: every image and video lives inside this repo.

## Current assets
All placeholders have been replaced with your real photos and video clips:

| File                               | Used for                             |
|-------------------------------------|----------------------------------------|
| `assets/img/portrait-suit.jpg`      | Hero background / hero video poster   |
| `assets/img/stage-agbada.jpg`       | About section, VVIP Unwind            |
| `assets/img/mayor-pitakwa.jpg`      | Mayor of Pitakwa                      |
| `assets/img/portrait-cream.jpg`     | KOYC Extraordinary                    |
| `assets/img/stage-mic.jpg`          | Gospel Geng Naija, live-strip poster  |
| `assets/img/portrait-brown.jpg`     | Talent Talk Tour (3pple T)            |
| `assets/img/stage-agbada-blue.jpg`  | Media reel grid (bonus shot)          |
| `assets/img/kobaba-logo.png`        | Nav, hero crest, footer               |
| `assets/video/kobaba-reel-1.mp4`    | Hero background loop (~12s, compressed) |
| `assets/video/kobaba-reel-2.mp4`    | Live-strip section loop (~12s, compressed) |

Want to swap any of these for a different shot later? Just replace the file
with the same name — no HTML editing needed. If a video file is ever
missing, the site automatically falls back to showing the matching photo
instead of a black box.

## Deploying to GitHub Pages with kobaba.com

1. Push this whole folder (including `assets/`, `CNAME`, and `index.html`)
   to a GitHub repo.
2. In the repo, go to **Settings → Pages** and set the source to the
   branch/folder you pushed to (e.g. `main` / root).
3. The included `CNAME` file already tells GitHub Pages the custom domain
   is `kobaba.com` — you don't need to re-type it in the Pages settings,
   but you can confirm it shows up there.
4. At your domain registrar, point `kobaba.com` at GitHub Pages:
   - Add **A records** for the apex domain (`kobaba.com`) to GitHub's Pages
     IPs: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`,
     `185.199.111.153`
   - If you also want `www.kobaba.com` to work, add a **CNAME record** for
     `www` pointing to `<your-github-username>.github.io`
5. Back in GitHub Pages settings, enable **Enforce HTTPS** once the domain
   is verified (may take a few minutes to a few hours after DNS propagates).

That's it — no server, no build process, no external asset dependencies.

