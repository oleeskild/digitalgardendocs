---
{"dg-publish":true,"permalink":"/advanced/content-customization/","created":"2022-11-09T22:06:14.364+01:00","updated":"2022-11-13T17:09:15.032+01:00"}
---


## Custom image width
The plugin supports setting width of images the same way you would do in Obsidian.

If you want a transluded image to have a size of 200 px, you would add the following:

![CleanShot 2022-11-13 at 16.48.36@2x.png|200](/img/user/img/CleanShot%202022-11-13%20at%2016.48.36@2x.png)

Your image should then be rendered with a max width of 200 px in your site. 

## Custom link title
The plugin supports setting a customer title the same way you would do in Obsidian.
If you have a note title `My Note` , but want a link to display `click here`, you would use the following syntax:

![CleanShot 2022-11-13 at 17.02.25@2x.png|300](/img/user/img/CleanShot%202022-11-13%20at%2017.02.25@2x.png)

## Tranclusions

By default, transclusion of other documents just renders the content as is. If you want to also include a heading on top of the transclusion you can do so by using the pipe character:
![CleanShot 2022-11-13 at 17.02.58@2x.png|300](/img/user/img/CleanShot%202022-11-13%20at%2017.02.58@2x.png)

This will add a h1 header with the value "Heading" at the start of your transclusion.

If you want the header to be equal to the title of the transcluded document, you can use this custom syntax:

![CleanShot 2022-11-13 at 17.03.59@2x 1.png|300](/img/user/img/CleanShot%202022-11-13%20at%2017.03.59@2x%201.png)

This will replace the heading with the title of the transcluded document when the note is published.

You can also use the title syntax inside other text:

![CleanShot 2022-11-13 at 17.04.18@2x.png|300](/img/user/img/CleanShot%202022-11-13%20at%2017.04.18@2x.png)


### Specifying heading level

You may also specify what heading level you want your transclusion to have. If you want the header to be a h2, you can use this syntax:
![CleanShot 2022-11-13 at 17.04.58@2x.png|300](/img/user/img/CleanShot%202022-11-13%20at%2017.04.58@2x.png)

h4 would look like this:

![CleanShot 2022-11-13 at 17.05.35@2x.png|300](/img/user/img/CleanShot%202022-11-13%20at%2017.05.35@2x.png)

### Default behaviour

By just using regular translucion, no header will be added:
![CleanShot 2022-11-13 at 17.05.52@2x.png|300](/img/user/img/CleanShot%202022-11-13%20at%2017.05.52@2x.png)

It's also worth noting that transclusions _do not need_ the dg-publish attribute. 

They behave the same as an image. If you transclude something into a document, and publish that document, everything that is transcluded in it will be published as if it was part of that note.
