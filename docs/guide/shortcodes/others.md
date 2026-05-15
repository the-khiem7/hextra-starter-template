> [!WARNING]
> Some of these are Hugo built-in shortcodes. These shortcodes are considered less stable and may be changed anytime.

## Badge

### Examples

- `default`
- `border`
- `color`
- `link`
- `icon`

### Usage

#### Default

- `Badge`

```
{{</* badge "Badge" */>}}
```

#### Colors

- `Badge`
- `Badge`
- `Badge`
- `Badge`
- `Badge`
- `Badge`
- `Badge`
- `Badge`
- `Badge`

```
{{</* badge content="Badge" */>}}
{{</* badge content="Badge" color="purple" */>}}
{{</* badge content="Badge" color="indigo" */>}}
{{</* badge content="Badge" color="blue" */>}}
{{</* badge content="Badge" color="green" */>}}
{{</* badge content="Badge" color="yellow" */>}}
{{</* badge content="Badge" color="amber" */>}}
{{</* badge content="Badge" color="orange" */>}}
{{</* badge content="Badge" color="red" */>}}
```

- `Badge`
- `Badge`
- `Badge`
- `Badge`
- `Badge`
- `Badge`
- `Badge`
- `Badge`
- `Badge`

```
{{</* badge content="Badge" border=false */>}}
{{</* badge content="Badge" color="purple" border=false */>}}
{{</* badge content="Badge" color="indigo" border=false */>}}
{{</* badge content="Badge" color="blue" border=false */>}}
{{</* badge content="Badge" color="green" border=false */>}}
{{</* badge content="Badge" color="yellow" border=false */>}}
{{</* badge content="Badge" color="amber" border=false */>}}
{{</* badge content="Badge" color="orange" border=false */>}}
{{</* badge content="Badge" color="red" border=false */>}}
```

#### Variants

- `Badge`
- `Releases`

```
{{</* badge content="Badge" icon="sparkles" */>}}
{{</* badge content="Releases" link="https://github.com/imfing/hextra/releases" icon="github" */>}}
```

### Options

| Name      | Description                                                                                                              |
|-----------|--------------------------------------------------------------------------------------------------------------------------|
| `content` | The text of the badge.                                                                                                   |
| `link`    | The link of the badge.                                                                                                   |
| `icon`    | The icon of the badge.                                                                                                   |
| `color`   | The color of the badge. <br/> `gray` (default), `purple`, `indigo`, `blue`, `green`, `yellow`, `amber`, `orange`, `red`. |
| `class`   | The class of the badge.                                                                                                  |
| `border`  | Adds or removes the border (default: true).                                                                              |
 
## YouTube

Embed a YouTube video.

```
{{</* youtube VIDEO_ID */>}}
```

Result:

YouTube video ID: `dQw4w9WgXcQ`

For more information, see [Hugo's YouTube Shortcode](https://gohugo.io/content-management/shortcodes/#youtube).

## PDF

With PDF shortcode, you can embed a PDF file in your content.

```
{{</* pdf "https://example.com/sample.pdf" */>}}
```

You can also place the PDF file in your project directory and use the relative path.

```
{{</* pdf "path/to/file.pdf" */>}}
```

Example:

PDF: https://upload.wikimedia.org/wikipedia/commons/1/13/Example.pdf
