# This solves the issue of running Puppeteer On ubuntu server (tried on Heroku)

### RUNNING PUPPETEER ON HEROKU REQUIRES A BUILD PACK.
- You can install the buildpack to your heroku Dyno by using the following command
` $ heroku buildpacks:add jontewks/puppeteer `
- Visit [Puppeteer buildpack git repo](https://github.com/jontewks/puppeteer-heroku-buildpack) forf more details.

### Even with the headless mode set to `true` , the program crashes because it cannot execute the chrome browser.
 So, in order to solve that issue, make the below changes to your puppeteer set up.

```
puppeteer: {
              headless: true,
              args: ['--no-sandbox','--disable-setuid-sandbox'],
              ...
           }
```
- What's **important** here is to specify the **value** for the `args` **option** as shown above with the `headless` **mode** always set to `true`. The rest of the options can be set to your requriements.
