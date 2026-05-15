> [!WARNING]
> Experimental feature. Not all cell types are supported.

[Jupyter Notebook](https://jupyter.org/) is a language-agnostic HTML notebook application for [Project Jupyter](https://jupyter.org/). It lets you create and share documents with live code, equations, visualizations, and narrative text.

## How to Use

### Using a Local Notebook

To use the Jupyter Notebook shortcode, place a notebook in your project. Similar to [adding images](../../organize-files#add-images), you can store notebooks in `assets/`.

```text
assets/
  notebook.ipynb
content/
  docs/
    my-page.md
```

Include the notebook in your page:

```markdown
---
title: My Page
math: true
---

{{%/* jupyter "notebook.ipynb" */%}}
```

You can also use [page bundles][page-bundles] to keep the notebook beside the Markdown file:

```text
content/
  docs/
    my-page/
      index.md
      notebook.ipynb
```

```markdown
---
title: My Page
math: true
---

{{%/* jupyter "notebook.ipynb" */%}}
```

### Using a Remote Notebook

You can also reference a remote notebook URL. For example:

```markdown
{{%/* jupyter "https://raw.githubusercontent.com/jupyter/notebook/main/docs/source/examples/Notebook/What%20is%20the%20Jupyter%20Notebook.ipynb" */%}}
```

## Example Notebook

> [!INFO]
> Example notebook source: `example.ipynb` in the project assets folder.

Notebook embed example:

```markdown
{{%/* jupyter "example.ipynb" */%}}
```

[page-bundles]: https://gohugo.io/content-management/page-bundles/#leaf-bundles
