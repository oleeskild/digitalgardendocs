---
{"dg-publish":true,"permalink":"/advanced/css-customization/"}
---

## Dynamic CSS/SCSS

Any css/scss files placed under `src/site/styles/user` will automatically be linked into the head right after all other styling. Meaning that the styling added here will take presedence over everything else. 

## Available css variables
Not all themes looks good out of the box. The template makes some css variables available to customize various css properties to customize it to your need.
Currently the available css variables are
`--graph-main`
`--graph-muted`


> [!note] The !important attribute
> Some styles uses the `!important` attribute. This is by most considered bad practice, but it is unfortunately neccessary in some places to override styling coming from whatever theme you've chosen. If your changes css changes doesn't reflect on your site, try adding an `!important` behind it and see if that helps. 


> [!warning] Deprecated
> Previously the only way to add custom styling to the site was to add styling to the `custom-styles.scss` file. This is still possible to do, but is considered deprecated.