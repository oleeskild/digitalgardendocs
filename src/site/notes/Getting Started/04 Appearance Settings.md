---
{"dg-publish":true,"permalink":"/getting-started/04-appearance-settings/","created":"2022-11-09T21:44:37.853+01:00","updated":"2023-03-09T15:21:41.781+01:00"}
---

The appearance settings can be accessed in the settings menu: 

![CleanShot 2022-11-13 at 13.54.28@2x.png](/img/user/img/CleanShot%202022-11-13%20at%2013.54.28@2x.png)

## Themes

Out of the box the digital garden has a simple dark theme applied. But the plugin supports using the community Obsidian themes. 

All community themes are supported. Some might look better than others. Themes can be selected in the "Theme" dropdown in the appearance settings:
![CleanShot 2022-11-13 at 13.55.43@2x 1.png](/img/user/img/CleanShot%202022-11-13%20at%2013.55.43@2x%201.png)
You can also select if you want the dark or ligth theme. If the theme doesn't support the base theme you've chosen, you will get a notification when applying the setting.

When you're done choosing a theme, click the "Apply settings to site" to make it go live. 

[Style settings](https://github.com/mgmeyers/obsidian-style-settings) are unfortunately not yet supported. This is on the development roadmap and will be added sometime in the future. 

## Sitename
You can set the name of your site in the "Sitename" setting. This will be displayed in the top navbar of your site.

Remember to click the "Apply settings to site" button after changing it. 
![CleanShot 2022-11-13 at 13.55.43@2x.png](/img/user/img/CleanShot%202022-11-13%20at%2013.55.43@2x.png)

## Favicon
You can set a custom SVG file as the favicon of your site. This is the icon that is showed in the browser tab before the page title. 

To do this, put an SVG file somewhere in your vault, and put the path to the SVG file in the "Favicon" setting.

Remember to click the "Apply settings to site" button after changing it. 
![CleanShot 2022-11-13 at 13.57.48@2x.png](/img/user/img/CleanShot%202022-11-13%20at%2013.57.48@2x.png)

## Timestamps Settings
Specify whether you want update and/or created time for your notes.

### Timestamp format
Specify in what format you want the time to be displayed. By default it will be shown like this: `Jan 01, 2020 1:30 PM`. 
If you want it to instead be displayed in a 24h format, you can use: `MMM dd, yyyy HH:mm`.

All the valid values for formatting the dates is available in the [luxon documentation](https://github.com/moment/luxon/blob/master/docs/formatting.md#table-of-tokens)

### Created and updated values
The date values can be set in two ways. Either be set as a front-matter value in your note, with the key you specify in the settings, like this:

![CleanShot 2023-03-09 at 15.09.43.png](/img/user/img/CleanShot%202023-03-09%20at%2015.09.43.png)

Or, of you want to use the creation and modification date of the file itself, leave these fields blanks, like this:
![CleanShot 2023-03-09 at 15.09.54.png](/img/user/img/CleanShot%202023-03-09%20at%2015.09.54.png)

## Note Icon Settings

Here you can specify if you want to show note icons in the note title, in the filetree and on internal links. Each note can have its own note icon. The plugin provides 4 icons by default. More details on that is available in [[Advanced/Note Specific Settings#Note Icons\|Note Specific Settings#Note Icons]].

Remember to click the "Apply settings to site" button after changing it. 
![CleanShot 2023-02-14 at 18.18.57@2x.png](/img/user/img/CleanShot%202023-02-14%20at%2018.18.57@2x.png)


[[Getting Started/03 Note settings\|< Prev]] | [[Getting Started/05 Other Settings\|Next: Other Settings >]]