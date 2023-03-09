---
{"dg-publish":true,"permalink":"/getting-started/01-getting-started/"}
---

The initial setup takes a couple of minutes, but when you're done you'll have a digital garden in which you are in control of every part of it, and can customize it as you see fit. Which is what makes digital gardens so delightful.

1. Download and install the community plugin [Digital Garden](obsidian://show-plugin?id=digitalgarden) in Obsidian.

--- 

2. Next, you will need a GitHub account. If you don't have this, create one [here](https://github.com/signup).

---

3. You'll also need a Vercel account. You can sign up using your GitHub account [here](https://vercel.com/signup)

---

4. Open [this repo](https://github.com/oleeskild/digitalgarden), and click the blue "Deploy to Vercel" button. 

![CleanShot 2023-01-22 at 23.38.57@2x.png](/img/user/img/CleanShot%202023-01-22%20at%2023.38.57@2x.png)
   This should open Vercel and create a copy of this repository in your GitHub accont. Give it a fitting name like 'my-digital-garden'. Follow the steps in Vercel to publish your site to the internet.
 
   --- 
   
5. Next you need to create an access token to your GitHub Account. This acts as a sort of password so that the plugin can add new notes to your GitHub repository on your behalf. Go to [this page](https://github.com/settings/tokens/new?scopes=repo) while logged in to GitHub. The correct settings should already be applied. (If you don't want to generate this every few months, choose the "No expiration" option.) Click the "Generate token" button, and copy the token you are presented with on the next page. 

> [!tip] A more secure option
> GitHub has recently launced a new beta feature, where you can target what repositories the token has access to. This is currently the most secure way to use the plugin. See [[Advanced/Fine grained access token\|Fine grained access token]] for details on how to generate this.


---

6. Open Obsidian and the settings for "Digital Garden" and fill in your GitHub username, the name of the repo with your notes which you created in step 3, and lastly paste in your token. 
   ![CleanShot 2022-11-09 at 21.08.36@2x.png](/img/user/img/CleanShot%202022-11-09%20at%2021.08.36@2x.png)
   
   ---
   
7. Now, let's publish your first note! Create a new note in Obsidian. And add this to the top of your file

```
---
dg-publish: true
dg-home: true
---
```

It should look something like this:

![CleanShot 2022-11-09 at 21.11.07@2x.png](/img/user/img/CleanShot%202022-11-09%20at%2021.11.07@2x.png)
**This does two things:**

* The dg-home setting tells the plugin that this should be your home page or entry into your digital garden. (It only needs to be added to _one_ note, not every note you'll publish).

* The dg-publish setting tells the plugin that this note should be published to your digital garden. Notes without this setting will not be published. (In other terms: Every note you publish will need this setting.)

--- 

8. Open your command pallete by pressing CTRL+P on Windows/Linux (CMD+P on Mac) and find the "Digital Garden: Publish Single Note" command. Press enter.

---

9. Go to your site's URL which you should find on [Vercel](https://vercel.com/dashboard). If nothing shows up yet, wait a minute and refresh. Your note should now appear.

---

Congratulations, you now have your own personal part of the internet in the form of a digital garden, for free 🎉.

You can now start adding links as you usually would in Obisidan, with double square brackets, to the note that you just published. 

Remember to also publish the notes your are linking to as this will not happen automatically. This is by design. You are always in control of what notes you actually want to publish. If you did not publish a linked note, the link will simply lead to a site telling the user that this note does not exist. 

If you want to unpublish a note, without deleting the note from your vault, simply remove the dg-publish: true attribute in the fronmatter, open the [[Getting Started/02 Commands#Open Publication Center\|publication center]] and click the "Delete notes from garden" button. 

Now that you are up and running, you can take a look at the available [[Getting Started/02 Commands\|commands]] or the various available [[Getting Started/03 Note settings\|note settings]]. Or maybe you want to [[Getting Started/04 Appearance Settings\|change your theme]]?

[[Getting Started/02 Commands\|Next: Commands >]]