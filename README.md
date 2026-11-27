# alonbabchuk.com

Source for [alonbabchuk.com](https://alonbabchuk.com), hosted on GitHub Pages.
GitHub builds the site with Jekyll on every push to `main`. You don't need to install
anything or run a build step locally.

## Folder structure

| Path | What it is |
|---|---|
| `_config.yml` | Site-wide settings: title, description, URL, language (en-GB), contact email, GitHub link. |
| `_data/navigation.yml` | The menu at the top of every page. |
| `_data/current_work.yml` | The three "Current work" cards on the home page. Edit the text and links here. |
| `_layouts/default.html` | The one shared page template: `<head>`, meta and Open Graph tags, notice bar, header, footer. |
| `_includes/notice.html` | The "under construction" bar at the top of every page. To remove it, delete the `{% include notice.html %}` line in `_layouts/default.html`. |
| `_includes/header.html`, `_includes/footer.html` | Site header (name and menu) and footer. |
| `assets/css/style.css` | All styling. Colours are defined as variables at the top. |
| `assets/fonts/` | Self-hosted Inter (body) and Source Serif 4 (headings), under the SIL Open Font License. No Google Fonts link is used. |
| `assets/img/photo.jpg` | *(Optional, not added yet.)* Add a portrait here and it appears automatically beside the home-page heading. A 4:5 crop works best. |
| `index.html` | Home page (`/`). |
| `research.md`, `writing.md`, `about.md`, `contact.md` | Inner pages (`/research/`, `/writing/`, `/about/`, `/contact/`). |
| `404.html` | "Page not found" page. |
| `favicon.svg` | Browser-tab icon (placeholder "AB"). Replace it with your own SVG of the same name. |
| `robots.txt` | Lets search engines crawl the site and points them to the sitemap. |
| `CNAME` | Custom domain for GitHub Pages. Don't delete it. |

`sitemap.xml` is generated automatically by the `jekyll-sitemap` plugin.

## Adding a new page

1. Create a Markdown file in the repo root, for example `projects.md`:

   ```markdown
   ---
   layout: default
   title: Projects
   description: One sentence for search engines and link previews.
   ---

   # Projects

   Write the content here in Markdown.
   ```

   It will be published at `/projects/`. The file name becomes the URL.

2. To put it in the top menu, add it to `_data/navigation.yml`:

   ```yaml
   - title: Projects
     url: /projects/
   ```

3. Commit and push. The page goes live within a minute or two:

   ```powershell
   git add .
   git commit -m "Add Projects page"
   git push
   ```

For a section with several pages, use a folder. For example, `research/prism.md` is published at `/research/prism/`.
Put PDFs and images in `assets/` (for example `assets/papers/my-paper.pdf`) and link to them as `/assets/papers/my-paper.pdf`.

## Project sites

Any other repo of yours that turns on GitHub Pages is served under this domain automatically.
For example, Pages on the `prism-safety` repo would appear at `alonbabchuk.com/prism-safety/`.

## Privacy

The site has no cookies, analytics or third-party scripts and loads no external fonts. Keep it that way when adding pages.
