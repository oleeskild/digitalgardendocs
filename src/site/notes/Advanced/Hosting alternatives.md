---
{"dg-publish":true,"permalink":"/advanced/hosting-alternatives/","dg-note-properties":{}}
---

While the [[Getting Started/01 Getting started\|01 Getting started]] uses Vercel as the hosting platform, the site can be run on any other hosting platform. Some alternatives are listed below. 

## Self hosting

### Local Export (no GitHub required)
The plugin has a built-in **Export Garden to Local Folder** command that writes all your published notes and images directly to a local copy of the [digitalgarden template](https://github.com/oleeskild/digitalgarden). This means you can build and host the site yourself without using GitHub as an intermediary.

1. Clone or download the [digitalgarden template](https://github.com/oleeskild/digitalgarden)
2. In the plugin settings, scroll to **Local Export** and set the folder path to where you cloned the template
3. Run the **Export Garden to Local Folder** command from the command palette
4. In the digitalgarden folder, run `npm install` then `npm run build` to generate the static site
5. Deploy the `dist/` folder to any static hosting provider or your own server

You can also use `npm run dev` to preview the site locally with hot reload before deploying.

> [!note]
> Publish status tracking and diffing are not available with local export. It performs a full export each time, which is fast since it's writing to local disk.

### Other self-hosting approaches
You can also use the approach explained in the [following GitHub discussion](https://github.com/oleeskild/obsidian-digital-garden/discussions/160)

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

### Blank garden
To deploy your site to Netlify instead of Vercel, follow the steps in [[Getting Started/01 Getting started\|01 Getting started]], but instead of using the "Deploy to Vercel" button in step 3, click the button below.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/oleeskild/digitalgarden)

## Others
The garden should work just fine with all static site hosting providers such as CloudFlare, Deno, Github Pages etc. Start by going to the [digitalgarden repo](https://github.com/oleeskild/digitalgarden) and clicking the Use This Template > Create a new repository. ![CleanShot 2023-05-23 at 22.43.25@2x.png](/img/user/img/CleanShot%202023-05-23%20at%2022.43.25@2x.png)
You should then be able to create an account with your hosting provider of choice and connect it to your newly created repository. If the setups asks for an install command, output directory or build command, use those that are visible in the picture from Vercel above. 