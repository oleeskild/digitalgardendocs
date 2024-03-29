---
{"dg-publish":true,"permalink":"/getting-started/06-updating-the-template/","created":"2022-11-10T14:34:31.728+01:00","updated":"2023-09-26T21:08:08.004+02:00"}
---


## Updating the template

In the setting menu for the plugin there is, in addition to the previously mentioned settings, a setting with the name "Update site to latest template" with a button saying "Create PR". Whenever this template receives any updates, this button can be used to update your site. It will create a new branch in your repo with the changes and create a Pull Request to your main branch. The plugin will present you with this URL in the setting view. 

If you used the "Deploy to Netlify" button, a Netlify bot will build a preview version of your site which you can visit to see that the changes does not contain any breaking changes. The URL should be visible in the PR. 
When you are ready you can use the "Merge pull request" button on the pull request page to merge the changes into your main branch and make the changes go live.

In the future you will be notified with a visual cue whenever there is an update ready. For now you will need to manually check. If you have the latest version, you will be told so.

### Screenshots of the process

![Updating the template](https://res.cloudinary.com/dix4ngy25/image/upload/q_auto/v1673511572/dgdocs/CleanShot_2023-01-11_at_22.06.35_2x_1.png)


## Modifying the template/site
The code for the website is available in the repo you created in step 3 in the [[Getting Started/01 Getting started\|getting started page]], and this is yours to modify however you want. 

If you want to make sure your changes doesn't get overwritten whenever you update the template again, see the following docs for how to apply customization without risking an overwrite on the next update:

[[Advanced/CSS Customization\|CSS Customization]]
[[Advanced/Adding custom components\|Adding custom components]]
[[Advanced/Content Customization\|Content Customization]]
[[Advanced/Configure build pipeline\|Configure build pipeline]]

[[Getting Started/05 Other Settings\|< Prev]]