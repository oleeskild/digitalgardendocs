---
{"dg-publish":true,"permalink":"/advanced/adding-custom-components/"}
---

Release 1.39.0 of the template introduced a new way to add custom components to your site. Previously, any customization done in the template would be overwritten whenever you [[Getting Started/06 Updating the template\|updated the template]], making it hard to maintain if you wanted the latest update.

The template now has a concept of slots, where you can add any content you want. Be it Javascript, HTML or CSS. 

### How does it work

#### Namespaces

These are the namespaces currently supported:

1.  common
2.  index
3.  notes

#### Slots

These are the supported slots:

1.  header
2.  afterContent
3.  footer

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

### Dynamic CSS/SCSS

Any css/scss files placed under `src/site/styles/user` will automatically linked into the head right after the `custom-styles.scss`.

### Caution

Remember that, the paths for a given slot are always sorted by filename. Therefore, if order matters, you should name files such they maintain the alphabetical order.