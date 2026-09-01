# Content guide

Everything on this site is plain HTML. To change text, open the `.html` file and
type over it — there is no build step, no framework, and nothing to install.

## Where each thing lives

| Page | File | What it holds |
|---|---|---|
| About / home | `index.html` | Portrait, one-paragraph pitch, links, news |
| Research | `research.html` | 2–4 project write-ups with figures |
| Publications | `publications.html` | Papers, preprints, conference abstracts |
| Talks | `talks.html` | Invited talks, contributed talks, posters |
| Teaching | `teaching.html` | Courses, mentoring, outreach |
| Styling | `assets/css/style.css` | All visual design, one file |
| Images | `assets/img/` | Portrait and project figures |
| Documents | `files/` | CV, slides, posters |

## Replacing the placeholders

Every placeholder is either in `SCREAMING CASE` (`UNIVERSITY`, `EMAIL@EXAMPLE.EDU`,
`MONTH YEAR`) or inside a dashed red box. To find what's left:

```sh
grep -rn "PLACEHOLDER\|EXAMPLE.EDU\|UNIVERSITY\|MONTH YEAR" *.html
```

Delete each `<div class="todo">…</div>` block once you've filled in that page.

## The pieces that matter most

1. **The lede on the home page.** Two sentences, no jargon. This is the single
   most-read text on the site.
2. **The CV PDF.** Linked from the nav of every page. A broken CV link is the
   worst possible first impression on a job-market site — add `files/cv.pdf`
   before publishing.
3. **Free-to-read links on every publication.** Preprint or accepted manuscript,
   even when the journal version is paywalled.
4. **A date in the footer.** An undated academic site reads as abandoned.

## Housekeeping

- The navigation is repeated at the top of each page. If you add or rename a page,
  update the `<nav>` block in all of them.
- The current page is marked with `aria-current="page"` — move it when you copy a
  page to make a new one.
- Images: replace the `.svg` placeholders with real `.jpg`/`.png` files and update
  the `src` attribute to match the new extension. Keep the portrait roughly square
  and under ~400 KB.
- Dark mode is automatic and follows the visitor's system setting. Colors are
  defined once at the top of `style.css`; `--accent` is the one to change to
  re-theme the whole site.

## Publishing on GitHub Pages

In the repository: **Settings → Pages → Build and deployment → Source: Deploy from
a branch**, then pick the branch and the `/ (root)` folder. The site appears at
`https://<username>.github.io/<repo>/` within a minute or two.

For a custom domain (e.g. `israelcyrineu.com`), add it under Settings → Pages,
point a CNAME record at `<username>.github.io` with the registrar, and leave
"Enforce HTTPS" checked. A personal domain is worth the ~$12/year on the job
market — it survives changing institutions.
