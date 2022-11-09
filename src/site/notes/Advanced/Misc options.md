---
{"dg-publish":true,"permalink":"/advanced/misc-options/"}
---

## Tranclusions

By default, transclusion of other documents just renders the content as is. If you want to also include a heading on top of the transclusion you can do so by using the pipe character:

```
![[Some Other Note|Heading]]
```

This will add a h1 header with the value "Heading" at the start of your transclusion.

If you want the header to be equal to the title of the transcluded document, you can use this custom syntax:

```
![[Some Other Note|{{title}}]]
```

This will replace the heading with the title of the transcluded document when the note is published.

You can also use the title syntax inside other text:

```
![[Some Other Note|This is a {{title}}]]
```

### Specifying heading level

You may also specify what heading level you want your transclusion to have. If you want the header to be a h2, you can use this syntax:

```
![[Some Other Note|##Heading]]
```

h4 would look like this:

```
![[Some Other Note|####Heading]]
```

### Default behaviour

By just using regular translucion, no header will be added:

```
![[Some Other Note]]
```

It's also worth noting that transclusions _do not need_ the dg-publish attribute. 

They behave the same as an image. If you transclude something into a document, and publish that document, everything that is transcluded in it will be published as if it was part of that note.


## Custom image width
The plugin supports setting width of images the same way you would do in Obsidian.

If you want a transluded image to have a size of 200 px, you would add the following:
```markdown
![[myimage.png|200]]
```
Your image should then be rendered with a max width of 200 px in your site. 