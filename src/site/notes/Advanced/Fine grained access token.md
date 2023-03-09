---
{"dg-publish":true,"permalink":"/advanced/fine-grained-access-token/","created":"2022-12-15T22:12:50.110+01:00","updated":"2023-01-10T23:02:42.487+01:00"}
---

Recently GitHub launched a more secure way to create an access token. Previously you would need to create a token that had access to all your repos. This isn't very secure, as a compromised token will give access to all of your repos. 

It's a bit more hassle, but you can now create an access token that only have access to the digital garden repo. This is the reccommended way to generate your token if you have more repos on your accounts. 

Remember to regenerate it after the expiration date, as it will no longer work after that date has passed.

To generate it, go to [this page](https://github.com/settings/personal-access-tokens/new), and apply settings as illustrated in the image below:


![CleanShot 2022-12-15 at 22.10.03@2x.png](/img/user/img/CleanShot%202022-12-15%20at%2022.10.03@2x.png)