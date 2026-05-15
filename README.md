# Hextra Starter Template

Minimal starter template for building a Hugo site with Hextra.

## Use this template

1. Click **Use this template** on GitHub
2. Create your new repository
3. Clone it locally
4. Run `hugo server -D`
5. Replace the sample content

## Starter content included

- Home
- About
- One sample blog post
- Three sample docs

## Suggested first edits

- Update site metadata in `hugo.yaml`
- Rewrite `content/_index.md`
- Replace `content/about/index.md`
- Rewrite or delete `content/blog/welcome.md`
- Rewrite the pages in `docs/`

## Local development

Prerequisites: [Hugo](https://gohugo.io/getting-started/installing/), [Go](https://golang.org/doc/install), and [Git](https://git-scm.com).

```shell
git clone <your-generated-repo-url>
cd <your-generated-repo>
hugo mod tidy
hugo server -D
```

## Deploy

This template can be deployed to any static host that supports Hugo, including GitHub Pages, Netlify, and Vercel.

## Update theme

```shell
hugo mod get -u
hugo mod tidy
```
