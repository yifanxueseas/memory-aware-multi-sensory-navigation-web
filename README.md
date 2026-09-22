# Anonymous Academic Project Page (GitHub Pages)

Static site for **double-blind** review of:

> Memory-Aware Multi-Sensor Perception for Efficient and Safe Navigation in Dynamic Environments

**Authors on this page must remain: Anonymous Authors only.**

---

## Deploy to a burner GitHub Pages account

1. Create a **new / burner** GitHub account (do not use your real identity or known username).
2. Create a public repository, e.g. `anon-nav-web` (any non-identifying name).
3. Upload the contents of this folder to the **repository root** (so `index.html` is at `/` of the repo, not nested).
4. In **Settings → Pages**: set Source to **Deploy from a branch**, branch `main` (or `gh-pages`), folder `/ (root)`.
5. Wait for the Pages URL: `https://<burner-user>.github.io/<repo>/`.
6. Submit that URL for review. Keep the account and repo free of personal names, emails, affiliations, and prior commits that deanonymize you.

Optional: enable a custom domain only if it does not reveal identity.

---

## Where to drop assets

| Asset | Path |
|-------|------|
| Paper PDF | `static/pdfs/paper.pdf` (anonymous camera-ready) |
| Fig. 1 overview | `static/images/fig1_overview.png` |
| Fig. 2 hospital / warehouse | `static/images/fig2_hospital.png`, `static/images/fig2_warehouse.jpg` |
| Fig. 3 trajectories | `static/images/fig3_trajectories.png` |
| Fig. 4 indoor / outdoor | `static/images/fig4_indoor.png`, `static/images/fig4_outdoor.png` |
| Teaser / sim / hardware videos | `static/videos/*.mp4` (see `static/videos/README.txt`) |
| Favicon | `static/images/favicon.svg` |

Camera-ready figures are wired in `index.html`. Do **not** include watermarks, lab logos, author faces, or institution names in media.

After dropping a teaser video, add a `<video>` tag in `index.html` pointing to `static/videos/teaser.mp4`.

---

## Anonymous code release (later)

For code, prefer an anonymous hosting option such as **[anonymous.4open.science](https://anonymous.4open.science/)** during review. Update the Code button only after the anonymous mirror is ready—**never** link a personal GitHub URL while under double-blind review.

---

## Anonymity grep checklist (run before publishing)

From the site root, search for forbidden identity tokens (prior-lab surnames, institution short name, prior GitHub handle, prior lab name). Example (split so this README itself stays clean):

```bash
# Build the forbidden-token list privately (do not paste real names into tracked files).
# Include prior surnames, institution short names, lab names, GitHub handles, and email local-parts.
rg -i -f /tmp/anon-forbidden.txt .
```

Expected: **zero matches** in HTML/CSS/JS/Markdown/SVG/images metadata (ignore third-party icon font false positives if any).

Also scan for your real name, email, lab, university, social handles, ORCID, and personal homepage URLs.
Never store the reconstructed token list inside this repository.

Additional checks:

- [ ] Meta tags use **Anonymous Authors**; `robots` is `noindex, nofollow`
- [ ] No Open Graph / Twitter cards with personal URLs
- [ ] No analytics (Statcounter, Google Analytics, etc.)
- [ ] No “More Works” / lab dropdown linking prior papers
- [ ] PDF and videos scrubbed of identifying metadata where feasible
- [ ] README / commit history on the burner repo do not reveal identity

---

## Local preview

Serve from the site root:

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

---

## License

Page layout adapted from the Academic Project Page Template / Nerfies-style academic pages (CC BY-SA 4.0). Paper content remains with the anonymous authors pending acceptance.
