# Publish and edit the portfolio with GitHub Pages

This portfolio is a static website. GitHub Pages can host it for free from a public repository. No server, database, package installation, or build command is required.

## Quickest task — change your displayed name

The name is controlled by one line in `content-data.js`. Changing it updates the large opening name, the browser-tab title, and the central figure's accessibility description.

### Change it directly on GitHub

1. Open your portfolio repository on GitHub.
2. Select the file named `content-data.js`.
3. Select the pencil icon labelled **Edit this file**.
4. Find this line near the top:

```js
name: "Meghvāhana Sānkr̥tyāyan",
```

5. Replace only the text between the quotation marks. For example:

```js
name: "Your New Name",
```

6. Select **Commit changes**.
7. Wait a few minutes and refresh the live website.

Keep the quotation marks and the comma at the end of the line.

## Part 1 — Publish the site

### 1. Extract the ZIP

Extract `portfolio-github-pages.zip` on your computer. Inside it you should see these files at the top level:

- `index.html`
- `content-data.js`
- `projects-data.js`
- `sky-data.js`
- `meghavahana-aura.png`
- `.nojekyll`
- `README.md`
- `GITHUB-GUIDE.md`

Do not upload the ZIP itself. Upload the extracted files.

### 2. Create a GitHub repository

1. Sign in at [github.com](https://github.com/).
2. Select the **+** menu in the upper-right corner and choose **New repository**.
3. Give it a simple name such as `portfolio`.
4. Set the repository to **Public** when using GitHub Free.
5. Select **Create repository**.

For the shortest possible address, name the repository `YOUR-USERNAME.github.io`. The resulting address will be `https://YOUR-USERNAME.github.io/`.

If you name it `portfolio`, the address will normally be `https://YOUR-USERNAME.github.io/portfolio/`.

### 3. Upload the files

1. Open the repository.
2. Select **Add file → Upload files**.
3. Drag all the extracted files into the upload area. Keep them at the repository root; do not place them inside another folder.
4. Enter a message such as `Upload portfolio`.
5. Select **Commit changes**.

### 4. Enable GitHub Pages

1. Open the repository's **Settings** tab.
2. In the left sidebar, select **Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
4. Select the `main` branch.
5. Select `/(root)` as the folder.
6. Select **Save**.

GitHub will display the website address in the Pages settings after deployment. The first deployment can take several minutes.

## Part 2 — Edit the four main sections

All four main sections are controlled by `content-data.js`. You do not need to edit `index.html`.

To edit it on GitHub:

1. Open `content-data.js` in the repository.
2. Select the pencil icon labelled **Edit this file**.
3. Change only the text between quotation marks.
4. Select **Commit changes**.
5. Wait briefly for GitHub Pages to republish the site.

### Change the name

The quick instructions at the beginning of this guide cover name changes. In summary, find:

```js
name: "Meghvāhana Sānkr̥tyāyan",
```

Replace the name inside the quotation marks.

### Add the CV

Upload your PDF into the repository root and call it `cv.pdf`. Then use:

```js
cv: {
  label: "CV",
  url: "cv.pdf"
},
```

You may also use a complete URL to a CV hosted elsewhere.

### Add the GitHub profile

Use your complete profile address:

```js
github: {
  label: "GitHub",
  url: "https://github.com/YOUR-USERNAME"
},
```

### Edit the author section

Change the author-page label or URL here:

```js
author: {
  label: "Author page",
  url: "https://example.com/author/",
```

Each article uses a title and URL:

```js
{
  title: "Article title",
  url: "https://example.com/article/"
}
```

Copy an entire article block to add another article. Put a comma between article blocks. Delete an entire block to remove an article.

If a section does not have a link yet, leave its URL empty:

```js
url: ""
```

## Part 3 — Edit Projects

Projects remain in `projects-data.js` so they are easy to add separately.

1. Open `projects-data.js` on GitHub.
2. Select the pencil icon.
3. Paste a project inside `window.portfolioProjects = [ ... ];`:

```js
{
  title: "Project name",
  description: "One short sentence about the project.",
  url: "https://example.com"
}
```

4. Put a comma between multiple project blocks.
5. Commit the change.

The project constellation and project list are generated automatically.

## Part 4 — Replace the central figure

Upload a replacement PNG using the exact filename `meghavahana-aura.png`. Commit the replacement and the live site will update automatically.

## Part 5 — Important editing rules

- Keep filenames unchanged unless you also update their references.
- Use straight quotation marks (`"`) in JavaScript files.
- Keep commas between repeated article or project blocks.
- Do not remove `.nojekyll`.
- Thunder begins only after the visitor selects **Thunder · On**, because browsers block automatic audio.
- Every committed change to `main` republishes the live site automatically.

## Troubleshooting

### The website shows a 404 page

Check **Settings → Pages** and confirm that the source is `main` and `/(root)`. Confirm that `index.html` is at the repository root.

### Images or animation data are missing

Confirm that `index.html`, `content-data.js`, `projects-data.js`, `sky-data.js`, and `meghavahana-aura.png` are all in the same folder.

### A recent edit is not visible

Wait a few minutes, refresh the page, and check the repository's **Actions** tab for the Pages deployment status.

### The page becomes blank after editing data

The usual cause is a missing quotation mark, brace, or comma in `content-data.js` or `projects-data.js`. Compare the edited block with the examples above.

## Official GitHub documentation

- [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [Configuring a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Editing repository files](https://docs.github.com/en/repositories/working-with-files/managing-files/editing-files)
