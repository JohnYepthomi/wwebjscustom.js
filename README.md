# This solves the issue of running Puppeteer On ubuntu server (tried on Heroku)

### Even with the headless mode set to `true` , the program crashes because it cannot execute the chrome browser.
 So, in order to solve that issue, make the below changes to your puppeteer set up.

```
puppeteer: {
        headless: true,
        defaultViewport: null,
        args: ['--no-sandbox','--disable-setuid-sandbox']
        }
```
- What's important here is to specify the value for the `args` option as shown above with headless always set to `true`. The rest of the options can be set to your requriements.
