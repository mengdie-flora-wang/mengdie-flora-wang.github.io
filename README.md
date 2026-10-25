# website-v6-polished — polished copy variant of the v5-refined timeline design

**Concept:** Light editorial "academic CV meets modern magazine" — experience and publications on a vertical timeline rail with year markers; Space Grotesk display + Inter body, indigo accent. Preview: open `index.html` via `file://` or `python3 -m http.server 8000 --bind 127.0.0.1`. Deploy: static files to any host (S3+CloudFront, GitHub Pages, Netlify).

## GitHub Pages

This is a static site: no dependencies or build step are required. All assets use relative paths so the site works under `/personal-website/`. `.nojekyll` tells Pages to serve the files directly.

Repository: https://github.com/farfallawang/personal-website

Expected site URL after publishing: https://farfallawang.github.io/personal-website/

The prepared repository preserves the bundle history and includes the newer wording from the supplied plain-files folder.

### Publish

1. Sign in to GitHub as an account with write access to `farfallawang/personal-website`.
2. From this directory, push `main`:

   ```sh
   git push -u origin main
   ```

3. In the repository's **Settings → Pages**, select **Deploy from a branch**, then **main** and **/ (root)**, and save.
4. Wait for the Pages deployment to finish, then visit the expected site URL above.

If using GitHub CLI, run `gh auth login` and `gh auth setup-git` before pushing. After the push, Pages can instead be enabled with:

```sh
gh api --method POST repos/farfallawang/personal-website/pages \
  -f 'source[branch]=main' -f 'source[path]=/'
```

For a repository where Pages is already enabled, use `--method PUT` to update its source. Future pushes to `main` publish automatically. Do not bypass any installed push approval hooks; obtain their required approval if a push is blocked.
