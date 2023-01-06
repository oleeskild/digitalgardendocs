---
{"dg-publish":true,"permalink":"/advanced/note-specific-settings/"}
---

## Title
If you want to use a custom page title instead of the name of your note, you can use the "title" attribute in frontmatter. This will then be used as the page title for the note. 

```
---
dg-publish: true
title: "My Custom Title"
---
```

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

