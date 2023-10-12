---
{"dg-publish":true,"permalink":"/getting-started/03-note-settings/","created":"2022-11-09T21:25:24.865+01:00","updated":"2023-10-12T17:02:52.890+02:00"}
---

By default the website is very simple, simply showing your note content, and a navbar at the top. But the plugin also support features like backlinks, local graph and search. 

All such settings are available in the "Note Settings" dialog. To edit them, got to Obsidian Settings > Digital Garden > Note Settings and click the "Edit" button as pictured below. 

![CleanShot 2022-11-09 at 21.27.43@2x.png](/img/user/img/CleanShot%202022-11-09%20at%2021.27.43@2x.png)

You should then be presented with a dialog looking like this:
![CleanShot 2022-11-09 at 21.38.15@2x.png](/img/user/img/CleanShot%202022-11-09%20at%2021.38.15@2x.png)

When these are turned on or off, the setting will instantly be published to your site. The settings set here are the global default settings used for each published note. If you want more granular control, and disable or enable some features for some particular notes, you can do this via front matter. All the settings has the frontmatter/[[Getting Started/01 Getting started#^ad515c\|properties]] equivalence written in paranthesis behind the settings. 

So if you have enabled the search globally, but have one note where you want to disable this, you can do so by setting the `dg-enable-search` to false:

```
dg-publish: true
dg-enable-search: false
```

Or the other way around: If you have disabled the graph globally, but have a note where you want it to show, you can set the `dg-show-local-graph` to true.

```
dg-publish: true
dg-show-local-graph: true
```

> [!note] Obsidian properties
> After introducing [properties](https://help.obsidian.md/Editing+and+formatting/Properties), Obsidian doesn't explicitly put the necessary "false" value on checkbox properties when they aren't checked. For now you'll need to use properties as text types when wanting to disable settings on a specific note. For example, the [[Example pages/Simple Page\|Simple Page]] note's properties looks like this:
> ![CleanShot 2023-09-21 at 10.41.39@2x.png](/img/user/CleanShot%202023-09-21%20at%2010.41.39@2x.png)

## Available settings

---

### Show home link
On by default. If this is turned on, a navbar will show at the top of each note. The site name will be displayed as a header, and can be clicked on. Clicking on it will take the user back to the home note. By default the site name is "Digital Garden". This can be changed via the [[Getting Started/04 Appearance Settings#Sitename\|04 Appearance Settings#Sitename]] settings. 

---

### Show local graph for notes
Off by default. When turned on a local graph, like the one in Obsidian, will be shown to the right. It will show both outgoing and incoming links to the current note. It is interactive, and can be moved around. Clicking one of the nodes will take you to the corresponding note.
On desktop it is shown to the right. On mobile it is shown in the bottom. 

---

### Show a table of content for notes
Off by default. When turned on, a list of all headers in your note will be shown to the right. Clicking one the headers will scroll to the corresponding header in the note.
On desktop it is shown to the right. On mobile it is hidden. 

---

### Show backlinks for notes
Off by default. When turned on, your published notes will display a list of notes linking back to it. It will only show notes that have been published. 
On desktop and bigger screens it will be placed on the right. On mobile and smaller screens it is put on the bottom of the page.

---

### Show inline title
Off by default. When turned on, the filename will be shown on the top of the page. Similar to the "Show inline title" setting introduced in Obsidian v1.0.

---

### Show filetree sidebar
Off by default. When turned on, a sidebar will be shown to the right, with all your published notes displayed in the folder hierarchy they are placed in in Obsidian. On smaller screens it will disappear, but can be viewed by clicking the "hamburger" menu in the top left corner.

---

### Link preview
Off by default. When turned on, all links will show a preview of the note content when you hover over them.

---

### Enable search
Off by default. When enabled, users have the option to easily search through all your published notes. The searchbox can be viewed by clicking the search box that appears in the upper right corner, or on the top of the filetree sidebar if this is enabled. It can also be triggerd by pressing CTRL+K on Windows/Linux or CMD+K on MacOS. 
A dialog will pop up. The results can be navigated by using your keyboard using the up and down arrow keys. Pressing enter will take you to the note. Pressing ESC will close the search box.

When search is enabled, you can also construct URLs that shows a search and the result. This is done by specifying a "q" query parameter in the URL. 
E.g. for this site: [https://dg-docs.ole.dev/?q=Commands](https://dg-docs.ole.dev/?q=Commands)

---

### Show Tags
Off by default. When turned on, any tags in your note's frontmatter will show at the top of the page, just under the note title. 
If search is enabled, clicking on a tag will bring up the search box and show all notes with that tag. 

---

### Let all frontmatter through
Off by default. Most users want this turned off. This is a setting mainly for advanced users, who modifies their template and wants full control over what frontmatter is passed through to the template. By default all frontmatter properties not recognized by the plugin are stripped away before publishing. This is to prevent the build in Netlify from failing if there are data in the frontmatter not recognized by the static site generator. (See [11ty Front Matter Data](https://www.11ty.dev/docs/data-frontmatter/) for details on this). If you're site suddenly stopped working, and this is enabled, it is worth trying to disable it again. 

---

## Note-specific settings
There are also some [[Advanced/Note Specific Settings\|Note Specific Settings]] that are not in the "Note Settings" view. These are settings that can only be set for specific notes. An overview of these are available [[Advanced/Note Specific Settings\|here]].


[[Getting Started/02 Commands\|< Prev]] | [[Getting Started/04 Appearance Settings\|Next: Appearance Settings >]]