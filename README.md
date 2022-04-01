# This solves the issue of running Puppeteer On ubuntu server (on Heroku atleast)

### Even with the headless mode set to `true` , the program crashes because it cannot execute the chrome browser.
 So, in order to solve that issue, make the below changes to your puppeteer set up.

```
puppeteer: {
        headless: true,
        defaultViewport: null,
        args: ['--no-sandbox','--disable-setuid-sandbox']
        }
