---
{"dg-publish":true,"permalink":"/getting-started/06-updating-the-template/"}
---


## Updating the template

In the setting menu for the plugin there is, in addition to the previously mentioned settings, a setting with the name "Update site to latest template" with a button saying "Create PR". Whenever this template receives any updates, this button can be used to update your site. It will create a new branch in your repo with the changes and create a Pull Request to your main branch. The plugin will present you with this URL in the setting view. 

If you used the "Deploy to Netlify" button, a Netlify bot will build a preview version of your site which you can visit to see that the changes does not contain any breaking changes. The URL should be visible in the PR. 
When you are ready you can use the "Merge pull request" button on the pull request page to merge the changes into your main branch and make the changes go live.

In the future you will be notified with a visual cue whenever there is an update ready. For now you will need to manually check. If you have the latest version, you will be told so.


## Modifying the template/site
The code for the website is available in the repo you created in step 3 in the [[Getting Started/01 Getting started\|getting started page]], and this is yours to modify however you want. If you know some css I encourage you to change the default styling to make the site your own. Please modify the custom-style.scss when doing so to avoid
future conflict when updating the template. Netlify should automatically update your site when you make changes to the code.

[[Getting Started/05 Other Settings\|< Prev]]