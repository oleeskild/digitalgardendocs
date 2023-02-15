---
{"dg-publish":true,"permalink":"/advanced/note-specific-settings/"}
---

## Title
If you want to use a custom page title instead of the name of your note, you can use the "title" attribute in frontmatter. This allows you to use characters that are not allowed to use in filenames. (Ex: ":", "/", "|") 

```
---
dg-publish: true
title: "My Custom Title"
---
```

---

## Custom Links

This plugin supports setting custom links to a note, if you prefer something else than the default behaviour. This is done by adding a dg-permalink attribute to the frontmatter of your file. As an example, the top of your file could look like this:

```
---
dg-publish: true
dg-permalink: "mynote"
---
```

This will make the URL to you note be "{Your-Garden-Name}.netlify.app/mynote/". You can still use normal obsidian links as before to link to it. These will be automatically corrected once you publish a note with the permalink attribute. Same goes for deleting the attribute. Doing so will result in the note using the default URL. All links in other notes should automatically be corrected and still work.

The permalinks can be an arbitrary level of folders deep, such as:

```
---
dg-permalink: "category/2022/mynote/"
---
```

---

## Metatags
Setting metatags for a note can be done by adding a dg-meta-tags attribute like so:

```
dg-meta-tags:
 description: "some description"
 "og:image": "https://example.com/someimage.png"
```

Note that there is a single space before the "description" field, **not** a tab. 

This feature can be used if you want custom titles and images when sharing links in social media. Using the example below will add a title and an image that will be used when sharing the link in social media. 

```
dg-meta-tags:
 "og:title": "Title Appearing on Social Media Site"
 "og:image": "https://example.com/someimage.png"
```

Read more about the [Open Graph Protocol](https://ogp.me/)

---
## Note Icons
Each note can have an assosiated note icon. By default this is set by the 
`dg-note-icon` property, but this can be changed in the [[Getting Started/04 Appearance Settings#Note Icon Settings\|note icon settings]]. 
By default the plugin provides 4 options: `default`, `1`, `2`, and `3`. 

The provided icons looks like this:

### Default

![](https://raw.githubusercontent.com/oleeskild/digitalgarden/3d0155d9923c36f3637f87bf45b7142c6162e608/src/site/img/default-note-icon.svg)

### 1
![](https://raw.githubusercontent.com/oleeskild/digitalgarden/3d0155d9923c36f3637f87bf45b7142c6162e608/src/site/img/tree-1.svg)

### 2
![](https://raw.githubusercontent.com/oleeskild/digitalgarden/3d0155d9923c36f3637f87bf45b7142c6162e608/src/site/img/tree-2.svg)

### 3

![](https://raw.githubusercontent.com/oleeskild/digitalgarden/3d0155d9923c36f3637f87bf45b7142c6162e608/src/site/img/tree-3.svg)

### Changing and adding icons
You can change and add your own icons the following way:

The ideal way to change the default icons is by adding the svgs in the img folder and setting the appropriate css vars in body in a [[Advanced/Adding custom components#Dynamic CSS/SCSS\|custom css file]]:

```css
body {
  --note-icon-1: url(/img/your-custom.svg);
  --note-icon-2: url(/img/tree-2.svg);
  --note-icon-3: url(/img/tree-3.svg);
  --note-icon-fallback: url(/img/default-note-icon.svg);}
}
```

To add new icons, let's say, for 'stone', add a snippet like this (and add the relevant svg) in a [[Advanced/Adding custom components#Dynamic CSS/SCSS\|custom css file]]:

```css
body.title-note-icon .cm-s-obsidian > header > h1[data-note-icon="stone"]::before,
body.filetree-note-icon .filename[data-note-icon="stone"]::before,
body.links-note-icon .internal-link[data-note-icon="stone"]::before {
  background-image: url(/img/stone.svg);
}
```