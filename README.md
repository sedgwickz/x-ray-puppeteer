# x-ray-puppeteer2

Inspired by [x-ray-chrome](https://github.com/ssbeefeater/x-ray-chrome), but optimized with iframe content auto loaded additionally.

## Install

`npm install x-ray-puppeteer2`

or

`yarn add x-ray-puppeteer2`

## Usage

```js
import Xray from "x-ray"
import XrayPuppeteer from "./x-ray-puppeteer.js"

const x = Xray().driver(
  XrayPuppeteer({
    executablePath: "/opt/homebrew/bin/chromium",
    cl: async (page, ctx) => {
      // do page operation here
      // parameters you can refer to: https://github.com/ssbeefeater/x-ray-chrome/blob/master/Readme.md
      await page.click("a.tab:nth-of-type(5)")
    },
  })
)

x("https://v2ex.com", "html", ["a.topic-link"])((err, obj) => {
  console.log(obj)
})
```
