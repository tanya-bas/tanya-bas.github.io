# Public website

This is one static website with three pages. GitHub Pages can serve it directly from this repository; `.nojekyll` tells GitHub Pages to serve these static files directly. No installation or build step is needed, and the pages work without JavaScript.

## Local preview

From this directory:

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Open http://localhost:8000. Stop with Ctrl+C. You can also open `index.html` directly, but use the server to test directory links.

## Where to edit

| Content | File |
| --- | --- |
| Introduction, profile links, public news timeline | `index.html` |
| Research and publications | `research/index.html` |
| Public writing index | `writing/index.html` |
| Shared design and mobile layouts | `assets/style.css` |

The navigation header is repeated in each HTML file. When changing navigation, update all three pages. Profile links live on Home. All internal paths are relative, so the site works at a domain root or a GitHub Pages repository subpath.

## Add a public update

In `index.html`, find `<ol class="timeline">`. Add a new item at the top, using the event date, newest first:

```html
<li>
  <time datetime="YYYY-MM">Month YYYY</time>
  <p>Your announcement, optionally linking to a paper, talk, or article.</p>
</li>
```

Use real dates, replace the example text, and preview before publishing. Keep updates to one or two sentences. The initial entries describe the verified July 2025 UNLP publication and November 2024 gender-bias paper. They are publication dates, not claims about when an announcement was originally posted.

## Add an article

Create `writing/your-article/index.html`, reuse a page's navigation header and document metadata, and replace its main content with the article. Since the article is two directories deep, use `../../assets/style.css`, `../../assets/favicon.svg`, `../../` for Home, `../../research/` for Research, and `../` for Writing. Give the article its own title, description, heading, and publication date.

Replace the empty state in `writing/index.html` with a dated link and short description of the article. No sample articles or invented writing have been published.

## GitHub Pages

GitHub Pages publishes the root of the `main` branch at https://tanya-bas.github.io/ from the repository `tanya-bas/tanya-bas.github.io`.

Commit and push changes to `main` to publish an update. Check the repository’s Pages deployment status after pushing.

## Content still to personalize

- Additional public updates as work develops.
- Which earlier research to retain or feature.
- First public essay or research note.

There is no CV page, Life page, login, or private content in this public implementation.

Publication sources:
- https://aclanthology.org/2025.unlp-1.2/
- https://arxiv.org/abs/2411.13738

Fonts load from Google Fonts with system fallbacks. Small WebP previews are used on the pages; research figures link to the original images.
