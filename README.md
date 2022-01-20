# Personal blog

Based on Jekyll with  [Chirpy theme](https://rubygems.org/gems/jekyll-theme-chirpy).

## Debug

- Build locally: `bundle exec jekyll s`
- Add new post: `_posts/YYYY-MM-DD-{slug}.md`

## Deploy

GitHub Pages is setup on the `gh-pages` branch.

To deploy changes:
- Push on `main`
- GitHub action `pages-deploy` triggered by `main` change: static files generated and pushed on `gh-pages`
- GitHub Pages action triggered by `gh-pages` change: static files deployed on the URL