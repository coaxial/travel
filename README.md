# Traviole

The Galoblog to share travel pictures.

# Usage

## Run locally

### Installing `hugo`

```
cd /tmp && wget -O - $(curl -s https://api.github.com/repos/gohugoio/hugo/releases/latest | grep "browser_download_url.*extended_[0-9].*linux-amd64.tar.gz" | cut -d '"' -f 4) | tar xf && sudo mv /tmp/hugo /usr/local/bin/hugo && cd -

```
`hugo version` should now work. It must be at least v0.138.0 extended.

### Run the dev server

`hugo -D` and open browser at http://localhost:1313

The dev version auto refreshes and updates with changes.

This will also show posts that have `draft = true` locally but they won't show in production unless `draft = false`.

## Create a new post

`$ hugo new content content/post/<post name>/index.md`

Then add images under `content/post/<post name>/<image name>`

## Include image in post

```markdown
{{< figure src="<image name>" title="Image title/description"
width="500px" >}}
```

For more shortcodes, see [Hugo docs](https://gohugo.io/content-management/shortcodes/) and [theme docs](https://stack.jimmycai.com/writing/shortcodes).

## Publish post

- Change `draft = true` to `draft = false` in the post's front matter
- Commit and push to branch
- Create a PR
- Review preview deploy in PR
- Iterate
- Merge to `master`
