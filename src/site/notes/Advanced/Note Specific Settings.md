---
{"dg-publish":true,"permalink":"/advanced/note-specific-settings/","created":"2022-11-09T22:05:34.872+01:00","updated":"2023-05-02T17:09:48.663+02:00"}
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

### File path
If you want your note to appear in a different file structure than what you have in your vault, you can use the dg-path attribute, like so:

```
---
dg-path: "Advanced/Features.md"
---
```

More details about this is available in [[Getting Started/05 Other Settings#Rewrite path for single note.\|05 Other Settings#Rewrite path for single note.]]

---

## Pinning notes to filetree
If you want certain notes to be at the top of the folder its in, you can use the dg-pinned attribute. Setting this to true will make the note be on top of the folder it is currently in

```
---
dg-pinned: true
---
```

---

## Hide file from file tree
If you want to hide a note from the filetree, you can do so by setting dg-hide to true.

```
---
dg-hide: true
---
```

---

## Hide note from graph
If you want to hide a note from the graph view, you can do so by setting dg-hide to true.

```
---
dg-hide-in-graph: true
---
```

---

## Metatags
Setting metatags for a note can be done by adding a dg-metatags attribute like so:

```
dg-metatags:
 description: "some description"
 "og:image": "https://example.com/someimage.png"
```

Note that there is a single space before the "description" field, **not** a tab. 

This feature can be used if you want custom titles and images when sharing links in social media. Using the example below will add a title and an image that will be used when sharing the link in social media. 

```
dg-metatags:
 "og:title": "Title Appearing on Social Media Site"
 "og:image": "https://example.com/someimage.png"
```

Read more about the [Open Graph Protocol](https://ogp.me/)

---

## Body classes
You can set custom classes to the body tag for your published notes, by using the 'dg-content-classes' attribute.

```
dg-content-classes: cards
```

This will add a "cards" class to your note, allowing you to customize each note with specific classes. 

You can also change the frontmatter key used to specify this in [[Getting Started/04 Appearance Settings#CSS settings\|the appearance settings]]. So, for example, if you are using [Minimal Theme's cssClasses](https://github.com/kepano/obsidian-minimal#css-helper-classes) you can change the key to 'cssClasses', meaning you don't have to specify the classes twice.

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
body.links-note-icon .internal-link[data-note-icon="stone"]::before,
body.backlinks-note-icon .backlink[data-note-icon="3"]::before {
  background-image: url(/img/stone.svg);
}
```