## Directory Structure

By default, Hugo searches for Markdown files in the `content` directory, and the structure of the directory determines the final output structure of your website.
Take this site as an example:

```text
content/
  _index.md
  docs/
    _index.md
    getting-started.md
    guide/
      _index.md
      organize-files.md
  blog/
    _index.md
    post-1.md
```

Each of the `_index.md` files is the index page for the corresponding section. The other Markdown files are regular pages.

```
content
├── _index.md // <- /
├── docs
│   ├── _index.md // <- /docs/
│   ├── getting-started.md // <- /docs/getting-started/
│   └── guide
│       ├── _index.md // <- /docs/guide/
│       └── organize-files.md // <- /docs/guide/organize-files/
└── blog
    ├── _index.md // <- /blog/
    └── post-1.md // <- /blog/post-1/
```

## Layouts

Hextra offers three layouts for different content types:

| Layout    | Directory             | Features                                                         |
| :-------- | :-------------------- | :--------------------------------------------------------------- |
| `docs`    | `content/docs/`       | Ideal for structured documentation, same as this section.        |
| `blog`    | `content/blog/`       | For blog postings, with both listing and detailed article views. |
| `default` | All other directories | Single-page article view without sidebar.                        |

To customize a section to mirror the behavior of a built-in layout, specify the desired type in the front matter of the section's `_index.md`.

```yaml
---
title: My Docs
cascade:
  type: docs
---
```

The above example configuration ensures that the content files inside `content/my-docs/` will be treated as documentation (`docs` type) by default.

## Sidebar Navigation

The sidebar navigation is generated automatically based on the content organization alphabetically. To manually configure the sidebar order, we can use the `weight` parameter in the front matter of the Markdown files.

```yaml
---
title: Guide
weight: 2
---
```

> [!INFO]
> It is recommended to keep the sidebar not too deep. If you have a lot of content, consider **splitting them into multiple sections**.

## Section Navigation

### Section Pagination Order

The order in which pages, accessed via [`PAGE.PrevInSection`](https://gohugo.io/methods/page/previnsection/) and [`PAGE.NextInSection`](https://gohugo.io/methods/page/nextinsection/) in a [page collection](https://gohugo.io/quick-reference/glossary/#page-collection), are ordered, is reversed by default.

To disable this reversed ordering you can set the `reversePagination` custom parameter in the page front matter to `false`. By default `reversePagination` is set to `true`.

#### Example

Given the following directory structure:

```text
content/
  _index.md
  blog/
    _index.md
    my-blog-series/
      _index.md
      post-a/
        index.md
      post-b/
        index.md
      post-c/
        index.md
```

And the following front matter in the posts:

```yaml
---
title: Post A
weight: 1
---
```
```yaml
---
title: Post B
weight: 2
---
```
```yaml
---
title: Post C
weight: 3
---
```

If the reader is at the bottom of `post-b/index.md`, they will see that the next page is `post-a`, and the previous page is `post-c`. This is due to `reversePagination` being set to `true` by default. This is ok when we want our posts to be displayed in chronological order from latest to oldest. However, in the case of a blog series where there are multiple parts, we typically want people to read the first post, and then move to the second and so on. So we want to disable the reversed ordering.

We can turn off `reversePagination` in every blog post in this series by adding the following front matter to `my-blog-series/_index.md`

```yaml
---
title: My Blog Series
cascade:
    params:
        reversePagination: false
---
```

We are using [`cascade`](https://gohugo.io/content-management/front-matter/#cascade-1) here to propagate the setting to all posts in the `my-blog-series` so that `reversePagination` is set to `false` for all descendents. This will now ensure that when the reader is on `post-b/index.md` they will see that the next page is `post-c` and the previous page is `post-a`.

## Breadcrumb Navigation

Breadcrumbs are auto-generated based on the directory structure of `/content`.

For example, consider the file structure [demonstrated above](#directory-structure). Given that structure, the breadcrumbs atop the page at `/docs/guide/organize-files/` would appear automatically as follows:

```
Documentation > Guide > Organize Files
```

### Customizing Breadcrumb Link Titles

By default, each breadcrumb link is generated based on that page's `title` parameter. You can customize this by specifying a `linkTitle`.

For example, if instead of `Organize Files` we wanted the breadcrumb to be `Foo Bar`:

```yaml
---
linkTitle: Foo Bar
title: Organize Files
---
```

This would now generate the following breadcrumbs:
```
Documentation > Guide > Foo Bar
```

### Enabling and Disabling Breadcrumbs

Whether breadcrumbs are enabled, or disabled, by default for a page, is determined by its [content type](https://gohugo.io/quick-reference/glossary/#content-type) and [page kind](https://gohugo.io/quick-reference/glossary/#page-kind):

|  Content Type   | Section  | Page      |
|:----------------|:--------:|:----------|
| `docs`          | Enabled  | Enabled   |
| `blog`          | Disabled | Enabled   |
| Any other type  | Disabled | Disabled  |

You can override these defaults on a page by setting `breadcrumbs` in its front matter:

```yaml
---
breadcrumbs: false
title: Organize Files
---
```

Similarly you can use [cascade](https://gohugo.io/content-management/front-matter/#cascade-1) to override the defaults on a page and its decendents:

```yaml
---
title: "Portfolio"

cascade:
  params:
    breadcrumbs: true
---
```

## Configure Content Directory

By default, the root `content/` directory is used by Hugo to build the site.
If you need to use a different directory for content, for example `docs/`, this can be done by setting the [`contentDir`](https://gohugo.io/getting-started/configuration/#contentdir) parameter in the site configuration `hugo.yaml`.

## Add Images

To add images, the easiest way is to put the image files in the same directory as the Markdown file.
For example, add an image file `image.png` alongside the `my-page.md` file:

```text
content/
  docs/
    my-page.md
    image.png
```

Then, we can use the following Markdown syntax to add the image to the content:

```markdown
![](image.png)
```

We can also utilize the [page bundles][page-bundles] feature of Hugo to organize the image files together with the Markdown file. To achieve that, turn the `my-page.md` file into a directory `my-page` and put the content into a file named `index.md`, and put the image files inside the `my-page` directory:

```text
content/
  docs/
    my-page/
      index.md
      image.png
```

```markdown
![](image.png)
```

Alternatively, we can also put the image files in the `static` directory, which will make the images available for all pages:

```text
static/
  images/
    image.png
content/
  docs/
    my-page.md
```

Note that the image path begins with a slash `/` and is relative to the static directory:

```markdown
![](/images/image.png)
```

[page-bundles]: https://gohugo.io/content-management/page-bundles/#leaf-bundles
