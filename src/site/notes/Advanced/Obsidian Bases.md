---
{"dg-publish":true,"permalink":"/advanced/obsidian-bases/"}
---

The plugin supports publishing Obsidian Bases — the database-like views that let you query, filter, and display notes based on their properties.

## How it works

Bases can be embedded in your notes as fenced code blocks:

````
```base
filters:
  file.inFolder("books")
views:
  - type: table
    name: "All Books"
    order:
      - file.name
      - author
      - rating
```
````

You can also embed standalone `.base` files using `![[MyBase.base]]`. The plugin will read the file and embed it as a code block during publishing.

> [!important] Published notes only
> Bases queries in your digital garden only run against notes that have been published (i.e. notes with `dg-publish: true`). Notes that exist in your vault but haven't been published will not appear in query results. This means the results on your garden may differ from what you see in Obsidian, where bases query all notes in your vault.

When you publish a note containing a base, the plugin passes all your note properties through to the published site. The base query runs at build time against all published notes, generating static HTML tables, cards, or lists.

## Properties

All frontmatter properties from your notes are automatically included when publishing. They are stored safely under the hood so they don't interfere with the site build — even properties like `date` that would normally cause issues.

This means if your notes have properties like `author`, `rating`, `status`, `genre`, etc., those will be available to base queries on the published site.

## Backlinks

Notes that appear in a base query result will show the page containing the base as a backlink. This works the same way as [[Advanced/Dataview queries\|dataview queries]].

## Supported features

### YAML Structure

| Feature | Supported | Notes |
|---------|-----------|-------|
| `filters` (global) | Yes | |
| `filters` (per-view) | Yes | |
| `formulas` | Yes | |
| `properties` (displayName) | Yes | |
| `summaries` (built-in) | Yes | Average, Sum, Min, Max, Range, Median, Stddev, Earliest, Latest, Checked, Unchecked, Empty, Filled, Unique, Count |
| `summaries` (custom with `values`) | No | Custom formula summaries not yet supported |
| `views` array | Yes | |

### View types

| View | Supported | Notes |
|------|-----------|-------|
| `table` | Yes | With column ordering, summaries, and grouping |
| `cards` | Yes | With `cardSize`, `image`, `imageFit`, `imageAspectRatio` |
| `list` | Yes | |
| `map` | No | |

When multiple views are defined, a dropdown selector appears (matching the Obsidian UI) that lets you switch between them.

### View options

| Option | Supported |
|--------|-----------|
| `name` | Yes |
| `type` | Yes |
| `order` (column list) | Yes |
| `sort` (property + direction) | Yes |
| `limit` | Yes |
| `groupBy` (property + direction) | Yes |
| `filters` (view-level) | Yes |
| `summaries` | Yes |

### Filters

| Feature                          | Supported                               |
| -------------------------------- | --------------------------------------- |
| `and` / `or` / `not`             | Yes                                     |
| `==`, `!=`, `>`, `<`, `>=`, `<=` | Yes                                     |
| `&&`, `\|\|`, `!`                | Yes                                     |
| `file.hasTag()`                  | Yes                                     |
| `file.inFolder()`                | Yes                                     |
| `file.hasProperty()`             | Yes                                     |
| `file.hasLink()`                 | Yes                                     |

### File properties

| Property                        | Supported | Notes                               |
| ------------------------------- | --------- | ----------------------------------- |
| `file.name`                     | Yes       |                                     |
| `file.path`                     | Yes       |                                     |
| `file.folder`                   | Yes       |                                     |
| `file.ext`                      | Yes       |                                     |
| `file.tags`                     | Yes       | From frontmatter                    |
| `file.size`                     | Partial   | Only if passed in metadata          |
| `file.ctime` / `file.mtime`     | Partial   | Via `created`/`updated` frontmatter |
| `file.links` / `file.backlinks` | Yes       | Computed from published notes        |
| `file.embeds`                   | No        |                                     |

### Global functions

| Function                                   | Supported |
| ------------------------------------------ | --------- |
| `today()`                                  | Yes       |
| `now()`                                    | Yes       |
| `date()`                                   | Yes       |
| `if()`                                     | Yes       |
| `number()`                                 | Yes       |
| `min()` / `max()`                          | Yes       |
| `list()`                                   | Yes       |
| `duration()`                               | No        |
| `link()` / `html()` / `image()` / `icon()` | No        |

### String methods

| Method | Supported |
|--------|-----------|
| `.contains()` | Yes |
| `.startsWith()` / `.endsWith()` | Yes |
| `.lower()` / `.upper()` / `.title()` | Yes |
| `.trim()` | Yes |
| `.split()` | Yes |
| `.replace()` | Yes |
| `.slice()` | Yes |
| `.length` | Yes |
| `.isEmpty()` | Yes |
| `.repeat()` / `.reverse()` | No |

### Number methods

| Method | Supported |
|--------|-----------|
| `.abs()` / `.ceil()` / `.floor()` | Yes |
| `.round()` | Yes |
| `.toFixed()` | Yes |
| `.isEmpty()` | Yes |

### List methods

| Method | Supported |
|--------|-----------|
| `.contains()` | Yes |
| `.containsAll()` / `.containsAny()` | Yes |
| `.join()` | Yes |
| `.sort()` / `.unique()` / `.flat()` / `.reverse()` | Yes |
| `.slice()` | Yes |
| `.length` / `.isEmpty()` | Yes |
| `.filter()` / `.map()` / `.reduce()` | No |

### Date fields & methods

| Feature | Supported |
|---------|-----------|
| `.year` / `.month` / `.day` | Yes |
| `.hour` / `.minute` / `.second` | Yes |
| `.format()` | Yes (basic tokens: YYYY, MM, DD, HH, mm, ss) |
| `.date()` | Yes |
| `.relative()` | Yes |
| Date arithmetic (`+ "1M"`, `- "1 week"`) | No |

Dates in the published site are formatted using your configured timestamp format from the plugin settings.

## Not yet supported

The following Obsidian Bases features are not yet available in the published garden:

- **Map view** — requires the Maps plugin
- **Date duration arithmetic** — `date + "1M"`, `now() - "1 week"`
- **`this` context** — referencing the file containing the base
- **List lambda methods** — `.filter()`, `.map()`, `.reduce()` with expressions
- **Rendering functions** — `html()`, `image()`, `icon()`, `link()`
- **`file.embeds`** — embedded file references
- **Custom summary formulas** — using the `values` keyword
- **`![[File.base#ViewName]]`** — embedding a specific view from a base file
