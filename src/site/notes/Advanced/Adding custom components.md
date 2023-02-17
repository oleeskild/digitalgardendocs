---
{"dg-publish":true,"permalink":"/advanced/adding-custom-components/"}
---

Release 1.39.0 of the template introduced a new way to add custom components to your site. Previously, any customization done in the template would be overwritten whenever you [[Getting Started/06 Updating the template\|updated the template]], making it hard to maintain if you wanted the latest update.

The template now has the concept of slots, where you can add any content you want. Be it Javascript, HTML or CSS. 

## Available slots

### Notes
### Namespaces
These are the namespaces currently supported for notes:
* common
	* Will be added on both the home page and all note pages
* index
	* Will be added on the home page
* notes
	* Will be added to alle note pages

#### Slots

These are the supported slots:

* head
	* Will be placed inside the html `<head>` tag
* header
	* Will be placed on top of the page, in the `<header>` tag, after tags and note title if that is enabled
* beforeContent
	* Will be placed just before the page content
* afterContent
	* Will be placed just after the page content
* footer
	* Will be placed in the footer of the page

### Filetree
#### Namespaces
* filetree

#### Slots
* beforeTitle
* afterTitle

### Sidebar
#### Namespaces
* filetree

#### Slots
* top
* bottom

## How does it work?

The files should be placed using the following format:

```
src/site/_includes/components/user/<namespace>/<slot>/<filename>.njk
```

The components are written in [Nunjuck](https://mozilla.github.io/nunjucks/), a templating language for HTML and Javascript. Don't worry if you don't know it. You don't have to use any of the features. Simply writing vanilla HTML will work. If you want to add a script, be sure to add it inside a script tag:
```html
<script>
	console.log("hello")
</script>
```

The important thing is that the fileextension used is "njk".

### Examples

For example to add common content in every pages header right after the title and tags the file should be placed in the following directory:

```
src/site/_includes/components/user/common/header/
```

Or,

Say, you have a comment system implemented in a file (e.g. `comment.njk`) and you want to use that only in notes pages, put it in the following path:

```
src/site/_includes/components/user/notes/footer/comment.njk
```

## Custom user data
If you want to compute some data in any of your custom `*.njk` files, you can modify the `src/helpers/userUtils.js` file. If you have the latest version of the template, it should look like this:
```javascript
// Put your computations here.

function userComputed(data) {
  return {};
}

exports.userComputed = userComputed;
```

Any properties added to the object return in the userComputed function, will be available to use in your `*.njk` files. As an example, the following `userUtils.js` file:
```javascript
// Put your computations here.

function userComputed(data) {
  return {
	  city: 'Bergen',
	  weather: ["rain", "rain", "rain"]
  };
}

exports.userComputed = userComputed;
```

..should make the city and weather property availble in your templates like so:
![CleanShot 2023-02-17 at 17.19.14.png](/img/user/CleanShot%202023-02-17%20at%2017.19.14.png)
## Dynamic CSS/SCSS


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/advanced/css-customization/#dynamic-css-scss" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



## Dynamic CSS/SCSS

Any css/scss files placed under `src/site/styles/user` will automatically be linked into the head right after all other styling. Meaning that the styling added here will take presedence over everything else. 


</div></div>



> [!info] File order
> Remember that, the paths for a given slot are always sorted by filename. Therefore, if order matters, you should name files such they maintain the alphabetical order.


## Examples in the wild
To get started and see a live example, take a look at GitHub user [uroybd](https://github.com/uroybd/topobon/tree/main/src/site/_includes/components/user) 's garden, [topobon](https://topobon.utsob.me/) . He uses components to add a theme switcher and a disqus comment section among other things. You can take a look at how he's imlemented it [here](https://github.com/uroybd/topobon/tree/main/src/site/_includes/components/user)