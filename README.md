# Songs of the Summer — Jekyll Site

This project is a mobile-friendly Jekyll site for publishing a ranked list of 10 songs of the summer. The song content is intentionally left as placeholders so you can add your own titles, performers, images, reviews, and ratings.

## Project structure

```text
songs-of-the-summer/
├── _config.yml
├── Gemfile
├── index.md
├── README.md
├── _layouts/
│   └── default.html
├── _songs/
│   ├── 01-song.md
│   ├── 02-song.md
│   ├── 03-song.md
│   ├── 04-song.md
│   ├── 05-song.md
│   ├── 06-song.md
│   ├── 07-song.md
│   ├── 08-song.md
│   ├── 09-song.md
│   └── 10-song.md
└── assets/
    ├── css/style.css
    └── js/main.js
```

## Create song content in Markdown

Each file in `_songs/` represents one song page. Keep the existing front matter at the top of each file and replace the placeholder values.

```yaml
---
layout: default
title: "Your Song Title"
performer: "Artist or Group"
rank: 1
cover_image: "/assets/images/your-image.jpg"
cover_alt: "Descriptive alt text for the image"
rating: 4
rating_label: "4 out of 5 stars"
permalink: /songs/your-song-slug/
---
```

### Front matter fields

- `title`: The song title displayed on the page.
- `performer`: The performer, band, or group.
- `rank`: The song's position in the top 10.
- `cover_image`: A path to the image. Store images in `assets/images/` and use a path beginning with `/assets/images/`.
- `cover_alt`: Accessible text describing the image.
- `rating`: A whole-number rating from 0 to 5. The template uses this to display filled and empty stars.
- `rating_label`: Text alternative for screen readers, such as `4 out of 5 stars`.
- `permalink`: The URL for the song page. Use lowercase words separated by hyphens.

### Write the review

After the closing `---`, write your review using normal Markdown. Add two or more paragraphs, headings, links, blockquotes, or lists as needed.

Example structure without actual review content:

```markdown
Your first review paragraph goes here.

Your second review paragraph goes here.
```

Do not remove the front matter delimiters (`---`). YAML values containing punctuation should remain inside quotation marks.

## Add images

Create an `assets/images/` folder and add your cover or related images there. Then reference an image like this:

```yaml
cover_image: "/assets/images/song-01.jpg"
```

Use appropriately licensed images, and write useful `cover_alt` text. If you do not want an image on a page, leave `cover_image` empty; the page will show a styled placeholder.

## Change the home page

Edit `index.md` to add your project title, introduction, methodology, publication date, or other editorial information. The homepage automatically lists all 10 files in `_songs/` in rank order.

## Run the site locally

Install Ruby and Bundler first. Then, from the project directory:

```bash
bundle install
bundle exec jekyll serve --livereload
```

Open the local URL shown in the terminal, usually:

```text
http://localhost:4000/
```

The `--livereload` option refreshes the browser when you save a file. Stop the server with `Ctrl+C`.

## Publish with GitHub Pages

1. Create a new GitHub repository. For a user site, use the repository name `<username>.github.io`. For a project site, any repository name works.
2. Copy all files in this project into the repository.
3. If this is a project site, update `url` and `baseurl` in `_config.yml`. For example:

   ```yaml
   url: "https://your-username.github.io"
   baseurl: "/your-repository-name"
   ```

   For a user site, set `baseurl: ""`.

4. Commit and push the files to GitHub.
5. In the repository, open **Settings → Pages**.
6. Under **Build and deployment**, choose **GitHub Actions**.
7. Add a Jekyll workflow if GitHub offers the starter workflow, or use the included `.github/workflows/jekyll.yml` file if present.
8. Wait for the workflow to finish. GitHub will display the published URL in **Settings → Pages**.

### Deploy from the command line

```bash
git init
git add .
git commit -m "Create Songs of the Summer site"
git branch -M main
git remote add origin https://github.com/your-username/your-repository.git
git push -u origin main
```

## Updating the ranking

To reorder songs, change each file's `rank` value. The homepage sorts the collection by that value. Update the visible rank label and page titles if you want the wording to match your ranking exactly.

## Licensing and attribution

Add image credits and any other attribution required by the licenses for media you use. Replace the placeholder site title, author information, social links, and metadata before publishing.