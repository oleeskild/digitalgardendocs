---
{"dg-publish":true,"permalink":"/advanced/hosting-alternatives/"}
---

While the [[Getting Started/01 Getting started\|01 Getting started]] uses Netlify as the hosting platform, the site can be run on any other hosting platform. Some alternatives are listed below. 

## Self hosting
If you want to host this on your own server, you can use the approach explained in the [following GitHub discussion](https://github.com/oleeskild/obsidian-digital-garden/discussions/160)

---

## Vercel

### Blank garden
To deploy your site to Vercel instead of Netlify, follow the steps in [[Getting Started/01 Getting started\|01 Getting started]], but instead of using the "Deploy to Netlify" button in step 3, click the button below.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/oleeskild/digitalgarden)

### Importing existing garden
Check if your garden has the "vercel.json" file in the root folder. 
![CleanShot 2023-01-06 at 15.11.11@2x.png](/img/user/img/CleanShot%202023-01-06%20at%2015.11.11@2x.png)

If not, add it, and copy the content from [here](https://github.com/oleeskild/digitalgarden/blob/main/vercel.json)
Then go to [https://vercel.com/new](https://vercel.com/new) and choose your digital garden repository from GitHub.

Verify that the following settings are set for "Build and Output" :
![CleanShot 2023-01-05 at 17.19.16.png](/img/user/img/CleanShot%202023-01-05%20at%2017.19.16.png)

Click "Deploy", and your site should be live. 

---

## Netlify
 > [!WARNING] Netlify Issues
> As of writing this on January 21st, 2023 there are some issues with Netlify, and this button won't create a copy. If that happens you will get an error when trying to deply your site. If you get an error in Netliify when using this, there is a workaround for this step [available here](https://github.com/oleeskild/obsidian-digital-garden/issues/167#issuecomment-1399222123)

### Blank garden
To deploy your site to Netlify instead of Vercel, follow the steps in [[Getting Started/01 Getting started\|01 Getting started]], but instead of using the "Deploy to Vercel" button in step 3, click the button below.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/oleeskild/digitalgarden)

## Cloudflare

> [!WARNING] Work in progress
> 🔧

## Deno

> [!WARNING] Work in progress
> 🔧


## Github Pages

> [!WARNING] Work in progress
> 🔧

