# ElectronTestApp

## install electron
```sh
npm -g i electron
```

## create project
```sh
mkdir hoge
cd hoge
npm init -y
touch index.js
touch index.html
```

## index.js
```js:index.js
let electron = require('electron');
let app = electron.app;
let BrowserWindow = electron.BrowserWindow;

let mainWindow = null;

app.on('window-all-closed', function() {
    if (process.platform != 'darwin')
    app.quit();
});

app.on('ready', function() {
    mainWindow = new BrowserWindow({width: 400, height: 300});
    mainWindow.loadURL('file://' + __dirname + '/index.html');

    mainWindow.on('closed', function() {
        mainWindow = null;
    });
});
```

## index.html
```html:index.html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Electron</title>
</head>
<body>
    <h1>Hello, world!</h1>
</body>
</html>
```

## run
```sh
electron .
```
