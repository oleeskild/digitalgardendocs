---
{"dg-publish":true,"permalink":"/advanced/tips-and-tricks/","created":"2022-11-09T22:09:04.283+01:00","updated":"2023-02-17T17:18:41.920+01:00"}
---

Here are a collection and tips and tricks that can be of use when publishing your notes. 

## Publish excalidrawing
If you want to publish a excalidrawing, without having to transclude it into another note, you can simply add the dg-publish: true flag to the frontmatter of the excalidraw file. It will then be published as a standalone note, with only the excalidrawing showing. 

---

## Mark multiple notes with dg-publish
The plugin itself doesn't provide any easy way to mark multiple notes at once with the dg-publish attribute. However you can make use of a plugin like [MetaEdit](https://github.com/chhoumann/MetaEdit) which has many features designed for exactly this. 

---

## Automatically add publish flag to note when adding note to folder
Some people have requested functionality for publishing all notes in a given folder. To do this, you can combine this plugin with the [Templater plugin](https://github.com/SilentVoid13/Templater) to create folders which will automatically use a template having the dg-publish attribute set. Thanks to [vanadium23](https://github.com/vanadium23) for [sharing this tip.](https://github.com/oleeskild/obsidian-digital-garden/issues/26#issuecomment-1114321275)

---

## Render HTML
If you write any HTML in your notes, they will be rendered in the garden. This means you can create custom "website-like" component on your site. As an example, the grid rendered  in [[Digital Garden Overview#Sites people have created\|Digital Garden Overview#Sites people have created]] was created using divs and image tags with some custom inline styling. 


```html
<div style="display: flex; flex-wrap: wrap; align-items: center; justify-content: center;">
	<div style="display: flex; flex-direction: column; justify-content: center;align-items:center;">
		<img style="padding: 10px" src="https://res.cloudinary.com/dix4ngy25/image/upload/c_scale,r_8,w_300/v1668068263/dgdocs/CleanShot_2022-11-10_at_09.17.28_2x.png"/>
		<a href="https://notes.thatother.dev/">That Other Dev</a>
	</div>
	<div style="display: flex; flex-direction: column; justify-content: center;align-items: center">
		<img style="padding: 10px" src="https://res.cloudinary.com/dix4ngy25/image/upload/c_scale,r_8,w_300/v1668068103/dgdocs/CleanShot_2022-11-10_at_09.14.47_2x.png"/>
		<a href="https://syleria.netlify.app/">Syleria</a>
	</div>
</div>
```

**Note that the HTML cannot have any empty newlines between the opening tag and closing tag. This will cause some of the HTML to be printed instead of rendered**


### Buttons
If you want to render buttons on your site, you can either do it the markdown way, with an SVG, or just create a html button. 

#### SVG Button
```markdown
[<img style="float:left" src="https://user-images.githubusercontent.com/14358394/115450238-f39e8100-a21b-11eb-89d0-fa4b82cdbce8.png" width="200">](https://ko-fi.com/oleeskild)
```

will result in

[<img style="float:left" src="https://user-images.githubusercontent.com/14358394/115450238-f39e8100-a21b-11eb-89d0-fa4b82cdbce8.png" width="200">](https://ko-fi.com/oleeskild)



### HTML Button

```html
<div style="display: flex; justify-content: center; cursor:pointer;">
	<a href="https://github.com/oleeskild/obsidian-digital-garden/issues/55" target="_blank">
		<button>Submit your site</button>
	</a>
</div>
```

will result in

<div style="display: flex; justify-content: center; cursor: pointer;">
	<a href="https://github.com/oleeskild/obsidian-digital-garden/issues/55" target="_blank">
		<button>Submit your site</button>
	</a>
</div>

### Styled HTML button

```html
<div style="display: flex; justify-content: center; cursor: pointer;">
	<a href="https://github.com/oleeskild/obsidian-digital-garden/issues/55" target="_blank">
		<button style=" font-size: 28px; padding: 10px; height: fit-content; margin-top: 50px; background: var(--text-accent); font-weight: 600; color: var(--text-on-accent); ">
			Submit your digital garden site
		</button>
	</a>
</div>
```

will result in 
<div style="display: flex; justify-content: center; cursor: pointer;">
	<a href="https://github.com/oleeskild/obsidian-digital-garden/issues/55" target="_blank">
		<button style=" font-size: 28px; padding: 10px; height: fit-content; margin-top: 50px; background: var(--text-accent); font-weight: 600; color: var(--text-on-accent); cursor: pointer;">
			Submit your digital garden site
		</button>
	</a>
</div>


---

### Page specific styling
Currently the plugin does not support setting custom styling using the [Style Setting Plugin](https://github.com/mgmeyers/obsidian-style-settings). But if you want some custom styling on some pages you can add an inline style tag at the bottom of the note. For example will the following text in the bottom of the note, align all headers in the center:
![CleanShot 2022-11-13 at 13.36.19@2x.png](/img/user/img/CleanShot%202022-11-13%20at%2013.36.19@2x.png)
It's a hacky workaround, but it works for simple things like custom styling to your home page. 

--- 

### Image heavy sites
The plugin in it's current form is not optimized for image-heavy sites. A couple of images in your notes should be just fine, but if you embed 10s or 100s of large image files in one note, you will run into some performance issues. 
The note will load slowly, and you can get an error from GitHub when trying to publish, due to the size of the note.

There is a workaround. If your notes has a lot of images, upload them to a  cloud storage and embed them with the `![image text](https://image.url)` syntax in your notes. You should then see a significant speed boost. 

This can even be automated by using a plugin like the [Obsidian Imgur Plugin](https://github.com/gavvvr/obsidian-imgur-plugin), which will automatically upload pasted images to imgur and embed them in your note. 

---

### Adding analytics to Vercel
If you are using Vercel to host your site, you can add basic analytics to your site by following the instructions described [here](https://github.com/oleeskild/obsidian-digital-garden/discussions/195)