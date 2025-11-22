# Blog

Hosted at https://pakkudon.github.io/blog/

This blog was built using [Hugo](https://gohugo.io/).

## Development
### Pre-requisites
- Install [`hugo`](https://gohugo.io/installation/) extended version (Application built using hugo v0.131.0, but may work with newer versions)

### Running it locally
1. Run [`hugo server`](https://gohugo.io/commands/hugo_server/).
2. Visit http://localhost:1313/blog/ to view changes.

### Adding new posts
1. Run `hugo new post/<date in YYYY-MM-DD>-<post slug>`
2. Edit new markdown file in `content/post/<date in YYYY-MM-DD>-<post slug>` directory

### Publishing changes
Changes pushed to `main` are automatically deployed to Github Pages. This is done via a workflow defined in [`.github/workflows/hugo.yml`](.github/workflows/hugo.yml).

### Pull latest updates for theme
Themes are installed as [git submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules). Run the following to pull in the latest commits for installed themes
```sh
git submodule foreach git pull origin master
```

### Update Hugo version
1. Download the latest available release from [https://github.com/gohugoio/hugo/releases](https://github.com/gohugoio/hugo/releases)
2. Install Hugo using your choice of package manager if required
3. Update `HUGO_VERSION` in [`.github/workflows/hugo.yml`](.github/workflows/hugo.yml) to ensure CI uses same Hugo version as local environment
```sh
# Example
curl -LJO https://github.com/gohugoio/hugo/releases/download/v0.141.0/hugo_0.141.0_linux-amd64.deb
sudo dpkg -i hugo_0.141.0_linux-amd64.deb
rm hugo_0.141.0_linux-amd64.deb
```

Alternatively, see [Hugo's docs](https://gohugo.io/installation/) for other methods
