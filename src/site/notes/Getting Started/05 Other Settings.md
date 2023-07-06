---
{"dg-publish":true,"permalink":"/getting-started/05-other-settings/","created":"2022-11-09T21:29:15.130+01:00","updated":"2023-05-23T22:58:33.266+02:00"}
---


## Slugify Note URL
The plugin "slugifies" your URLs by default. In essence this means that a note with the path "My Folder/My Note.md" will get the URL "my-folder/my-note". 
You can disable this by turning this setting off. 

> [!faq] Non-English Characters
> Slugifying the URL causes some non-English characters, like Chinese characters, to disappear. Resulting in all notes getting an empty URL. If you've experienced this issue, disabling this setting should fix that.


![CleanShot 2022-12-18 at 13.09.33@2x.png](/img/user/img/CleanShot%202022-12-18%20at%2013.09.33@2x.png)

---

## Rewrite Paths
If you want your filepaths in the garden to differ from the vault path, you can add rewrite rules in the "Path Rewrite Rules" section. If, let's say, I want to change the Getting Started folder to instead be named "Quick Start" in the garden it would look like this:
![CleanShot 2023-05-23 at 22.47.43@2x.png](/img/user/img/CleanShot%202023-05-23%20at%2022.47.43@2x.png)

![CleanShot 2023-05-23 at 22.48.16@2x.png](/img/user/img/CleanShot%202023-05-23%20at%2022.48.16@2x.png)

After adding this, all affected notes should show up as changed in the publication center, allowing you to update them. 

### Rewrite path for single note.
You can also change the note on a per note basis. Using `dg-path` in the frontmatter, you can change where a note should be located in the garden. This will overwrite any rules that may apply to that note. 
The dg-path property needs the entire filepath you want. For example, if I wanted the "Features" note to instead be located under the "Advanced" folder in the garden I would add the following frontmatter to it:

```
---
dg-path: "Advanced/Features.md"
---
```

---
## Custom filters
If you want any of your content to be modified before publishing the note, you can add a filter.

![CleanShot 2023-05-23 at 22.50.21@2x.png](/img/user/img/CleanShot%202023-05-23%20at%2022.50.21@2x.png)

For example say you want to hide text that is inside a specific pattern:
```
This is some normal text.

::: hidden
This is some private text that should not be published.
:::
```

You could then add the following filter.

![CleanShot 2023-05-23 at 22.53.24@2x.png](/img/user/img/CleanShot%202023-05-23%20at%2022.53.24@2x.png)
It also supports Regex groups, meaning you can use $1, $2 etc in the replacement string to insert the first and second regex group and so on. 

 [[Getting Started/04 Appearance Settings\|< Prev]] | [[Getting Started/06 Updating the template\|Next: Updating the template >]]