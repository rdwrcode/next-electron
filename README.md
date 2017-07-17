# next.js + electron.js

this app is built by following this [link](https://leo.im/2017/electron-next).

## setup
```
git clone https://github.com/electron/electron-quick-start
yarn
yarn add --dev next@beta react react-dom
yarn add electron-next electron-is-dev
```

* electron-next: ensures that Electron can handle next.js' output in the renderer
* electon-is-dev: change the main process' behavior depending on the environment the application is running in

Now let's check.
```
npm start
```
Do you get this?
![hello](https://github.com/rdwrcode/next-electron/raw/master/images/hello-electron.png "Hello Electron")




