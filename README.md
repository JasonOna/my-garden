# Quartz v4

> “[One] who works with the door open gets all kinds of interruptions, but [they] also occasionally gets clues as to what the world is and what might be important.” — Richard Hamming

Quartz is a set of tools that helps you publish your [digital garden](https://jzhao.xyz/posts/networked-thought) and notes as a website for free.

🔗 Read the documentation and get started: https://quartz.jzhao.xyz/

[Join the Discord Community](https://discord.gg/cRFFHYye7t)

## Sponsors

<p align="center">
  <a href="https://github.com/sponsors/jackyzha0">
    <img src="https://cdn.jsdelivr.net/gh/jackyzha0/jackyzha0/sponsorkit/sponsors.svg" />
  </a>
</p>

## Publish to GitHub Pages

You can publish a Quartz site to GitHub Pages. Quartz writes its static output to the `public` directory, and the repository already contains a GitHub Actions workflow to build and deploy `public` using the `actions/deploy-pages` action.

- Ensure `configuration.baseUrl` in `quartz.config.ts` is set to your Pages URL (example: `username.github.io/repo-name`) or to your custom domain. Quartz uses this value for RSS, sitemap and to generate a `CNAME` file when appropriate.
- If you want a custom domain, set `configuration.baseUrl` to that domain (for example `example.com`) and Quartz's CNAME emitter will write a `CNAME` file into the `public` output on build.
- This repo includes a `.nvmrc` (Node 24). To develop locally using `nvm`:

```bash
nvm install 24
nvm use 24
npm ci
npx quartz build    # outputs to ./public
node ./quartz/bootstrap-cli.mjs build    # alternative for running without engine checks
```

- The GitHub Actions workflow that builds and deploys to Pages is at [.github/workflows/deploy-pages.yml](.github/workflows/deploy-pages.yml). It triggers on pushes to `main` by default — change the branch in that file if you deploy from another branch.

- After pushing to GitHub, enable Pages under your repository Settings → Pages (source: GitHub Actions). If you configure a custom domain in the Pages settings, GitHub will manage TLS and DNS validation for that domain.

If you'd like, I can also add a short example `CNAME` commit step or update `docs/hosting.md` to explicitly point to this repository workflow — tell me which you prefer.
