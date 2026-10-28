# naomi-gendler.com

This folder is a static academic website: plain HTML and one stylesheet, with no build step. It is meant to be hosted on GitHub Pages at the custom domain naomi-gendler.com.

## Files

| File | Contents |
| --- | --- |
| `index.html` | The home page: bio, contact links, research areas, and recent and upcoming news |
| `research.html` | Descriptions of the three research themes, each with key papers |
| `publications.html` | The full publication list, numbered as in the CV |
| `talks.html` | Invited plenary talks, colloquia and seminars, and contributed talks |
| `teaching.html` | Teaching, mentoring, outreach and professional service |
| `Gendler_CV.pdf` | The CV, linked from every page |
| `assets/style.css` | All styling for every page, including dark mode and phone layout |
| `assets/favicon.svg` | The browser-tab icon, a reflexive lattice hexagon |
| `assets/headshot.jpg` | (Optional; not yet added.) A portrait, about 4:5. If the file exists, it appears on the home page automatically. |
| `404.html` | The page shown for broken links |

Until the domain is set up, the site is live at https://nvgendler.github.io/naomi-gendler.com/. There is deliberately no `CNAME` file yet: with one, GitHub would redirect that address to naomi-gendler.com before the domain exists.

## Routine updates

- **New paper:** add an `<li class="pub">` block at the top of the right year in `publications.html`, and optionally a news line in `index.html`.
- **New talk:** add an `<li>` at the top of the right list in `talks.html`.
- **New CV:** replace `Gendler_CV.pdf`, keeping the file name the same so that the links keep working.
- Change the "Updated" date in the footers when you make substantive changes.

## Previewing locally

```bash
python3 -m http.server 8137 --directory ~/naomi-gendler.com
```

Then open http://localhost:8137 in a browser.

## Putting it online at naomi-gendler.com

1. **Register the domain.** As of 28 October 2026, naomi-gendler.com is unregistered. Buy it from any registrar, for example Cloudflare Registrar, Porkbun or Namecheap. It costs roughly $10–15 per year.
2. **Repository and Pages (done 28 October 2026).** The site is in the public repository `nvgendler/naomi-gendler.com`, and GitHub Pages deploys it from `main` at `/ (root)`.
3. **Point the domain at GitHub.** At the registrar, add these DNS records:

   | Type | Name | Value |
   | --- | --- | --- |
   | A | `@` | `185.199.108.153` |
   | A | `@` | `185.199.109.153` |
   | A | `@` | `185.199.110.153` |
   | A | `@` | `185.199.111.153` |
   | AAAA | `@` | `2606:50c0:8000::153` |
   | AAAA | `@` | `2606:50c0:8001::153` |
   | AAAA | `@` | `2606:50c0:8002::153` |
   | AAAA | `@` | `2606:50c0:8003::153` |
   | CNAME | `www` | `nvgendler.github.io` |

   If you use Cloudflare, set these records to "DNS only" (grey cloud) so that GitHub can issue the HTTPS certificate.
4. **Set the custom domain.** In the repository, go to Settings → Pages, enter `naomi-gendler.com` under "Custom domain", and save. GitHub commits a `CNAME` file for you, so pull before editing locally again.
5. **Turn on HTTPS.** Once DNS has propagated, which usually takes minutes to an hour, tick "Enforce HTTPS" on the Pages settings page.
6. **Verify the domain (recommended).** In your GitHub account settings, go to Pages → "Add a domain" and add the TXT record it gives you. Verification stops anyone else's repository from claiming the domain if Pages is ever switched off.

## After launch

- Change the website line in the CV source from `naomigendler.wixsite.com/home` to `naomi-gendler.com`, then replace `Gendler_CV.pdf`.
- Update the website field on INSPIRE, ORCID and any job-application portals.
- On the old Wix site, add a line saying the site has moved to naomi-gendler.com. Free Wix sites cannot redirect automatically.
