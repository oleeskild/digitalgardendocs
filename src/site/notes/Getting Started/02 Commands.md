---
{"dg-publish":true,"permalink":"/getting-started/02-commands/"}
---


### Publish Active Note
Will publish the currently active note, and only this. `dg-publish: true` must be set on the active note.


---

### Add publish flag
This will automatically add a `dg-publish: true` to the frontmatter in the currently active note. 

---

### Quick Publish And Share Note
Will add a publish flag to the currently active note, publish it and copy the garden URL to your clipboard.

It essentially works the same way as manually triggering the commands `Add Publish Flag --> Publish Single Note --> Copy Garden URL` in sequnce.

--- 

### Publish All Notes Marked for Publish 
This command will publish all notes in your vault that have the dg-publish setting set to true. Depending on the number of notes, this may take a while. You can watch the progress of publication in the bottom right statusbar. 

---

## Copy Garden URL 
This will copy the URL of the currently active note to your clipboard.
Make sure you have the correct Base URL in your settings, so that the copied URL is correct.

---

### Open Publication Center
This will open the publication center dialog. Here you can view a list what files are published, changed, deleted and not yet published. You also have the option to mass-update your notes from here. 

---

### Export Garden to Local Folder
Exports all notes marked with `dg-publish: true` and their images to a local folder on your computer. This is useful for self-hosting your garden or previewing it locally without publishing to GitHub.

Before using this command, set the path to your local [digitalgarden](https://github.com/oleeskild/digitalgarden) folder in the plugin settings under **Local Export**.

After exporting, run `npm run dev` in your digitalgarden folder to preview the site with hot reload.

> [!note]
> This command is only available on desktop. Publish status tracking and diffing are not available with local export — it performs a full export each time.


 [[Getting Started/01 Getting started\|< Prev]] | [[Getting Started/03 Note settings\|Next: Note Settings >]]