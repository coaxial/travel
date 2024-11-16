# Traviole

The Galoblog to share travel pictures.

# Usage

## Run locally

### Install `hugo`

```
cd /tmp && wget -O - $(curl -s https://api.github.com/repos/gohugoio/hugo/releases/latest | grep "browser_download_url.*extended_[0-9].*linux-amd64.tar.gz" | cut -d '"' -f 4) | tar xf && sudo mv /tmp/hugo /usr/local/bin/hugo && cd -

```
`hugo version` should now work. It must be at least v0.138.0
extended.

### Run the dev server

`hugo server -D` and open browser at http://localhost:1313

The dev version auto refreshes and updates with changes.

This will also show posts that have `draft: true` locally but they
won't show in preview norproduction unless `draft: false`.

## Create a new post

### Make a branch

`$ git checkout master && git pull && git checkout -b <branch
name>`

### Create the files

Decide which of the two gallery types you want (see [docs](https://github.com/nicokaiser/hugo-theme-gallery?tab=readme-ov-file#usage) and run the command (use `index.md` or `_index.md` depending on gallery type)

`$ hugo new content content/<gallery name>/index.md`

Then add images under `content/<gallery name>/<image name>`

See [theme docs](https://github.com/nicokaiser/hugo-theme-gallery?tab=readme-ov-file#usage) for the file organization structure.

### Edit the post

If server not started: `hugo server -D`, visit
http://localhost:1313/

Edit file at `content/<gallery name>/index.md` (see [theme frontmatter docs](https://github.com/nicokaiser/hugo-theme-gallery?tab=readme-ov-file#front-matter).)

## Include images in post

Put the images in the gallery's directory and order them using the frontmatter in `index.md` (featured image is the cover image, resources array orders images. See [theme docs](https://github.com/nicokaiser/hugo-theme-gallery?tab=readme-ov-file#usage).

## Prepare post publication

- `$ git add . && git commit -m "Descriptive commit message"`
- On GitHub, create a pull request
- Wait for it to build and check the preview link in the comment
- Iterate

## Publish post to prod
- Change `draft: true` to `draft: false` in post's frontmatter
- Commit and push change to branch
- Merge to `master` (will autodelete the branch and push to prod)
