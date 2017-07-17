# next.js + electron.js

this app is built by following this [link](https://leo.im/2017/electron-next).

## 1 setup
```
git clone https://github.com/electron/electron-quick-start
yarn
yarn add --dev next@beta react react-dom
yarn add electron-next electron-is-dev
```

* electron-next: ensures that Electron can handle next.js' output in the renderer
* electon-is-dev: changes the main process' behavior depending on the environment the application is running in

Now let's check.
```
npm start
```

![hello](https://github.com/rdwrcode/next-electron/raw/master/images/hello-electron.png "Hello Electron")

## 2 renderer
Use [now-desktop](https://github.com/zeit/now-desktop) as an example.

```
mkdir renderer && cd renderer
mkdir pages && cd pages
```

then create start.js as the entry point for next.js and create next.config.js inside renderer to let next.js know where to find start.js.

change main.js to get next.js called.
* import electron-next
```
const prepareNext = require('electron-next')
```
* replace the existing event listener 
```
app.on('ready', createWindow)
```
with 
```
app.on('ready', async () => {
  await prepareNext('./renderer')
  createWindow()
})
```

Then modify loadURL in main.js. Run it.

![hello](https://github.com/rdwrcode/next-electron/raw/master/images/hello-next.png "Hello Next")

## 3 production
```
yarn add --dev electron-builder
```
modify pacakge.json



