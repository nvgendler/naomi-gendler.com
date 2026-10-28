# naomi-gendler.com

This folder is a static academic website: plain HTML and one stylesheet, with no build step. It is meant to be hosted on GitHub Pages at the custom domain naomi-gendler.com.

## Files

| File | Contents |
| --- | --- |
| `index.html` | The home page: bio, contact links, research areas, and recent and upcoming news |
| `research.html` | Descriptions of the three research themes, each with key papers |
| `publications.html` | The full publication list, numbered as in the CV |
| `talks.html` | Recorded talks (video cards that play in place), then invited plenary talks, colloquia and seminars, and contributed talks, with a "Video" link on each talk that has a recording |
| `assets/talks/` | Thumbnails for the recorded-talk cards (640 × 360) |
| `teaching.html` | Teaching, mentoring, outreach and professional service |
| `cooking-gardening.html` | A photo gallery in two sections, garden and kitchen. Clicking a photo opens it in a full-screen viewer, and each photo's `alt` text doubles as its caption there. |
| `assets/cooking-gardening/` | The gallery photos: `name.jpg` (1600 pixels on the long side, for the viewer) and `name-sm.jpg` (800 pixels, for the grid). All photo metadata, including GPS location, has been removed. |
| `Gendler_CV.pdf` | The CV, linked from every page |
| `assets/style.css` | All styling for every page, including dark mode and phone layout |
| `assets/favicon.svg` | The browser-tab icon, a reflexive lattice hexagon |
| `assets/headshot.jpg` | The portrait on the home page: 600 × 750 pixels, with all photo metadata (including GPS location) removed. To change it, replace it with another 4:5 photo of the same name, and strip location data first. If the file is missing, the home page simply shows no photo. |
| `404.html` | The page shown for broken links |

The site is live at https://naomi-gendler.com/. The old address, https://nvgendler.github.io/naomi-gendler.com/, redirects there.

## Routine updates

- **New paper:** add an `<li class="pub">` block at the top of the right year in `publications.html`, and optionally a news line in `index.html`.
- **New talk:** add an `<li>` at the top of the right list in `talks.html`. If it was recorded, add `<a class="tag tag-link" href="VIDEO-URL">Video</a>` right after its title.
- **New featured video:** save the thumbnail as `assets/talks/VIDEO-ID.jpg` (YouTube's is at `https://i.ytimg.com/vi/VIDEO-ID/maxresdefault.jpg`), then copy an `<article class="video">` block in `talks.html` and change the ID, title, event and running time. Keep the number of cards even, so the two-column grid stays complete.
- **New gallery photo:** remove its location data first (iPhone photos record GPS coordinates), save both sizes in `assets/cooking-gardening/`, and copy an existing `<a>…</a>` line in `cooking-gardening.html`, changing the file names, `alt` text, `width` and `height`.
- **New CV:** replace `Gendler_CV.pdf`, keeping the file name the same so that the links keep working.
- Change the "Updated" date in the footers when you make substantive changes.

## Previewing locally

```bash
python3 -m http.server 8137 --directory ~/naomi-gendler.com
```

Then open http://localhost:8137 in a browser.

## Hosting and domain (set up 28 October 2026)

- **Domain:** naomi-gendler.com, registered at Porkbun (registry expiry 28 October 2027). Keep auto-renew on at Porkbun, because a lapsed domain can be registered by someone else.
- **Hosting:** GitHub Pages deploys the public repository `nvgendler/naomi-gendler.com` from `main` at `/ (root)`. The `CNAME` file tells Pages to serve the custom domain; don't delete it.
- **HTTPS:** enforced. GitHub issues and renews the certificate automatically.
- **DNS records at Porkbun** (for reference, if they ever need to be re-entered):

  | Type | Host | Answer |
  | --- | --- | --- |
  | A | *(blank)* | `185.199.108.153` |
  | A | *(blank)* | `185.199.109.153` |
  | A | *(blank)* | `185.199.110.153` |
  | A | *(blank)* | `185.199.111.153` |
  | AAAA | *(blank)* | `2606:50c0:8000::153` |
  | AAAA | *(blank)* | `2606:50c0:8001::153` |
  | AAAA | *(blank)* | `2606:50c0:8002::153` |
  | AAAA | *(blank)* | `2606:50c0:8003::153` |
  | CNAME | `www` | `nvgendler.github.io` |

- **Still recommended: verify the domain with GitHub.** In your GitHub account settings, go to Pages → "Add a domain", enter `naomi-gendler.com`, and add the TXT record it shows at Porkbun. Verification stops anyone else's repository from claiming the domain if Pages is ever switched off.

## After launch

- Update the website field on INSPIRE, ORCID and any job-application portals.
- On the old Wix site, add a line saying the site has moved to naomi-gendler.com. Free Wix sites cannot redirect automatically.
