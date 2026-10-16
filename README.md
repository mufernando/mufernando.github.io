# m-rodrigues.me

Personal academic website of Murillo F. Rodrigues, built with [Hugo](https://gohugo.io/) and the
[Hugo Blox](https://hugoblox.com/) Academic CV template (Bootstrap v5 module).

## Local preview

Requires Hugo **extended 0.124.1** (same version as the GitHub Actions deploy) and Go (for Hugo modules).

```sh
hugo server            # http://localhost:1313, reloads on save
hugo server -D         # also show drafts
```

Pushing to `main` deploys to GitHub Pages via `.github/workflows/publish.yaml` (takes a few minutes).

## Adding publications

Publications are generated from `publications.bib`.

1. **Add the entry to `publications.bib`** (e.g. export from Zotero). Check that:
   - the citation key looks like `author_word_year` — it becomes the page folder
     (`rodrigues_census_2026` → `content/publication/rodrigues-census-2026/`);
   - the author list is complete (no `and others`, which shows up as "Others");
   - there are no escapes like `{\textgreater}` in the abstract (write `>` instead).
2. **Push to `main`.** The *Import Publications From Bibtex* workflow opens a PR
   ("Hugo Blox Builder - Import latest publications") that adds the new page.
3. **Before merging that PR**, in each new `content/publication/<name>/index.md`, replace
   your name in `authors:` with `admin`:
   ```yaml
   authors:
   - Jane Doe
   - admin          # was: Murillo F. Rodrigues
   ```
   This highlights your name and enables the author-role badge.
4. Merge. The homepage shows the 10 most recent papers; all are on `/publication/`.

**Author roles.** First- and last-author papers are detected automatically from where `admin`
appears in `authors:`. Shared roles go in `data/author_roles.yaml`, keyed by folder name:

```yaml
gower-accessible-2025: co-first
miranda-gene-2026: co-last
some-paper-2027: none        # no badge
```

**Updating an existing paper** (e.g. preprint → journal). The workflow only adds *new* papers.
To refresh existing pages, run the importer locally and redo step 3 for every page:

```sh
pip install academic==0.10.0
academic import publications.bib content/publication/ --compact --overwrite
```

If a citation key changes (e.g. a new preprint version), delete the old folder so the paper
isn't listed twice.

## Adding posts

Posts are currently hidden: the Posts block and menu item were removed, and
`content/post/hello-world` is a draft.

1. **Create** `content/post/<slug>/index.md` (copy `hello-world/index.md` as a template),
   set `title`, `date`, `summary`, and `draft: false`, then write the post in Markdown below
   the front matter. Put images in the same folder; a `featured.jpg` becomes the post's banner.
2. **Show posts on the site** (first time only):
   - in `content/_index.md`, add a block under `sections:`
     ```yaml
     - block: collection
       id: posts
       content:
         title: Recent Posts
         filters:
           folders:
             - post
         count: 5
       design:
         columns: '1'
         view: compact
     ```
   - in `config/_default/menus.yaml`, add
     ```yaml
     - name: Posts
       url: '#posts'
       weight: 40
     ```
3. Preview with `hugo server`, then push to `main`.

## Where things live

| What | Where |
| --- | --- |
| Bio, role, social links | `content/authors/admin/_index.md` |
| Profile photo | `content/authors/admin/avatar.jpg` (square, ~1200px) |
| CV | `static/uploads/resume.pdf` |
| Research themes | `content/project/<name>/index.md` + image in the same folder |
| Homepage sections and order | `content/_index.md` |
| Navbar | `config/_default/menus.yaml` |
| Colors / fonts | `data/themes/genomics.toml`, `data/fonts/genomics.toml` |
| Custom styling | `assets/scss/custom.scss` |
| Theme template overrides | `layouts/` |
