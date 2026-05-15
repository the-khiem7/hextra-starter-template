A built-in component to show important information to the reader.

> [!NOTE]
> [GitHub-style alerts](../../markdown#alerts) are supported since [v0.9.0](https://github.com/imfing/hextra/releases/tag/v0.9.0).
> It leverages Markdown syntax to render the callout which ensures better portability and readability of the content.

## Examples

> [!NOTE]
> A **callout** is a short piece of text intended to attract attention.

> [!INFO]
> A **callout** is a short piece of text intended to attract attention.

> [!WARNING]
> A **callout** is a short piece of text intended to attract attention.

> [!ERROR]
> A **callout** is a short piece of text intended to attract attention.

> [!IMPORTANT]
> A **callout** is a short piece of text intended to attract attention.

### Default

> [!NOTE]
> A **callout** is a short piece of text intended to attract attention.

```markdown
{{</* callout */>}}
  A **callout** is a short piece of text intended to attract attention.
{{</* /callout */>}}
```

### Info

> [!INFO]
> A **callout** is a short piece of text intended to attract attention.

```markdown
{{</* callout type="info" */>}}
  A **callout** is a short piece of text intended to attract attention.
{{</* /callout */>}}
```

### Warning

> [!WARNING]
> A **callout** is a short piece of text intended to attract attention.

```markdown
{{</* callout type="warning" */>}}
  A **callout** is a short piece of text intended to attract attention.
{{</* /callout */>}}
```

### Error

> [!ERROR]
> A **callout** is a short piece of text intended to attract attention.

```markdown
{{</* callout type="error" */>}}
  A **callout** is a short piece of text intended to attract attention.
{{</* /callout */>}}
```

### Important

> [!IMPORTANT]
> A **callout** is a short piece of text intended to attract attention.

```markdown
{{</* callout type="important" */>}} 
  A **callout** is a short piece of text intended to attract attention.
{{</* /callout */>}}
```

### Custom Icon

> [!NOTE]
> A **callout** is a short piece of text intended to attract attention.

```markdown
{{</* callout icon="sparkles" */>}}
  A **callout** is a short piece of text intended to attract attention.
{{</* /callout */>}}
```

> [!IMPORTANT]
> A **callout** is a short piece of text intended to attract attention.

```markdown
{{</* callout type="important" icon="sparkles" */>}}
  A **callout** is a short piece of text intended to attract attention.
{{</* /callout */>}}
```

### Emoji

A **callout** is a short piece of text intended to attract attention.

```markdown
{{</* callout emoji="🌐" */>}}
  A **callout** is a short piece of text intended to attract attention.
{{</* /callout */>}}
```

A **callout** is a short piece of text intended to attract attention.

```markdown
{{</* callout type="info" emoji="ℹ️" */>}}
  A **callout** is a short piece of text intended to attract attention.
{{</* /callout */>}}
```

## Options

| Parameter | Description                                                                     |
|-----------|---------------------------------------------------------------------------------|
| `type`    | The type of callout. (default, `info`, `warning`, `error`, `important`)         |
| `emoji`   | The emoji to show before the callout.                                           |
| `icon`    | The icon to show before the callout. (related to type or can be a custom icon). |
