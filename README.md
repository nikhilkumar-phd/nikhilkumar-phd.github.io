# nikhilkumar-phd.github.io

Static site. No build step — plain HTML and CSS, served directly by GitHub Pages.

## Files

```
index.html          About / landing
projects.html       Research (anchors: #test-platform #conformal-dynamic #traction-reducing
                    #traction-enhancing #wear-optimisation #conformal-static
                    #uae-diagnostics #directions)
publications.html   Journal articles, conference papers, dissertation
teaching.html       Teaching philosophy, experience, courses
education.html      CV — positions, education, funding, skills
contact.html        Contact
assets/css/site.css Single stylesheet, all pages
assets/js/site.js   Mobile nav toggle only
assets/files/CV.pdf ← add your CV here
assets/papers/      ← paper PDFs; see PUT-PDFS-HERE.txt for exact filenames
img/profile.jpg     ← already in your repo; keep it
img/research/       ← 11 PNGs + 1 MP4 + poster; see "Research media" below
```

## Deploy

1. Copy these files into the root of the `nikhilkumar-phd.github.io` repo, replacing the old ones.
2. Keep your existing `img/profile.jpg`.
3. Drop your CV at `assets/files/CV.pdf`.
4. Commit and push to `main`. Pages redeploys in about a minute.

Old URLs (`projects.html`, `publications.html`, `education.html`, `contact.html`) are preserved, so
nothing you've already shared will break.

## Before you publish — placeholders to replace

Search the files for `EDIT ME`:

- **index.html** — "Outside the lab" paragraph
- **teaching.html** — the mentoring paragraph (your statement has bracketed alternatives; pick one)
- **publications.html** — VTechWorks permalink for the dissertation

## Paper PDFs

Every publication links to both a DOI and a local PDF. The links are already wired up —
`assets/papers/PUT-PDFS-HERE.txt` lists the exact filename each one expects, plus which
version of each paper you're allowed to host. Short version:

- The four MDPI / Springer papers are open access, so the publisher PDF is fine.
- The three Zenodo deposits are your own uploads, so those are fine too.
- The Taylor & Francis paper (IJRT) is the exception: post your **accepted manuscript**,
  not their typeset PDF, and fill in the publication date in the acknowledgement line
  that's already on the page.

Until the PDFs are in place those links will 404. Delete the `PUT-PDFS-HERE.txt` file
when you're done.

## Research media

Each research entry shows two figures. `projects.html` already points at these
exact filenames in `img/research/` — all lowercase, case-sensitive on Pages:

```
test-platform-1.png          test-platform-2.png
conformal-dynamic-1.png      conformal-dynamic-2.png
traction-reducing-1.png      traction-reducing-2.png
traction-enhancing-1.png     traction-enhancing-2.png
conformal-static-1.png       conformal-static-2.png
uae-diagnostics-1.png        uae-diagnostics-2.mp4
                             uae-diagnostics-2-poster.png
```

Images: 1200x900 PNG (4:3), under 300 KB each. CSS crops to 4:3 and centre-cuts
anything else.

The wear-optimisation entry has no figures by design.

### The video slot

`uae-diagnostics-2.mp4` is set to autoplay, muted, looping, inline — it behaves
like a GIF. If your clip has narration or runs longer than ~15 seconds, remove
`autoplay loop` from the `<video>` tag in `projects.html` so it waits for a click.

Encoding: H.264 MP4, 4:3, 1200x900 or smaller, under 10 MB. GitHub Pages caps
files at 100 MB, but anything over ~10 MB makes the page slow on mobile. Strip
the audio track if it's silent — it saves space and guarantees autoplay works.

The poster is the still shown before playback. Export a representative frame at
1200x900 PNG. If you skip it, delete the `poster` attribute rather than leaving
it pointing at a missing file.

## Design notes

- Fonts: Archivo (display), Source Serif 4 (body), IBM Plex Mono (data and labels), loaded from Google Fonts.
- Accent colour `#ce1b52` is the magenta of pressure-sensitive contact film — change `--film` in
  `site.css` to reskin the whole site.
- The hero diagram is inline SVG, so it scales and stays crisp. Edit it directly in `index.html`.
