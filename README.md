# Blog

Hosted at https://pakkudon.github.io/blog/

This blog was built using [Hugo](https://gohugo.io/).

## Development
### Pre-requisites
- Install [`hugo`](https://gohugo.io/installation/) extended version (Application built using hugo v0.92.2, but may work with newer versions)

### Running it locally
1. Run [`hugo server`](https://gohugo.io/commands/hugo_server/).
2. Visit http://localhost:1313/blog/ to view changes.

### Adding new posts
#### For text-only posts
1. Run `hugo new post/<post slug>.md`
2. Edit new markdown file in `content/post` directory

#### For posts that have related assets
1. Run `hugo new --kind post-bundle post/<post slug>`
2. Edit new markdown file in `content/post/<post slug>` directory

### Publishing changes
Changes pushed to `main` are automatically deployed to Github Pages. This is done via a workflow defined in [`.github/workflows/hugo.yml`](.github/workflows/hugo.yml).
