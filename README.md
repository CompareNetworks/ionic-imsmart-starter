# ionic-imsmart-starter

## To Start an Ionic Project for imSMART

### Install the Latest Version of Ionic

```console
npm i -g @ionic/cli
```

Integrate your new app with Capacitor to target native iOS and Android? (y/N)

### Intiate the Ionic Project

Initiate the Ionic project. Below names the project "ionic-imsmart" and sets the type to "tabs." Don't install dependencies now since we will be later after making changes.

```console
ionic start ionic-imsmart tabs  --type=angular --no-deps
```

### Change Directory to the Newly Created Project

A new directory with the name of the project will have been created. In this case, the name of the directory is "ionic-imsmart", the following commands/changes will be made inside of that folder. Replace "ionic-imsmart" with the name of the project you created in the command below:

```console
cd ./ionic-imsmart
```

### OPTIONAL - Update package.json to use Ionic 4

Ionic 5 currently has issues with ion-icons displaying on imSMART. Update the package.json to downgrade to the latest version of Ionic 4.

In the package.json file, delete the following line from "dependencies" (leave any other properties)

```json
"dependencies": {
    "@ionic/angular": "^5.0.0",
  }
```

Add the following line back (leave any other properties)

```json
"dependencies": {
    "@ionic/angular":"4.11.10",
  }
```

Note: After this only the icons of ion-icons 4 will be available.

### Install the imSMART NPM Module

In the directory you created by ionic, you will install the imsmart repository. You will need access to the private imSMART NPM account to install the imsmart

```console
npm install @comparenetworks/imsmart-web --save
```

### Install the rest of the NPM modules

In the directory you created by ionic, you will install the imsmart repository. You will need access to the private imSMART NPM account to install the imsmart

```console
npm install
```

### Update index.html to run inside the imSmart App

In the index.html file, delete the following line (leave any other properties)

```html
<base href="/" />
```

Add the following line back (leave any other properties)

```html
<base href="./" />
```

### Using macs inside the imSmart App

1. Create a `declarations.d.ts` inside the `src` folder. And add following line to it.

```js
declare var macs: any;
```

2. Copy `macs.js`(Added to the repo) file under `src/assets/js/` folder. 
3. Add following line just before the `</head>` tag in the `index.html` file which is located in `src` folder.

```html
<script type="text/javascript" src="assets/js/macs.js"></script>
```

Usage: 
```js
var jsonObj = {
    url : "https://postman-echo.com/post",
    method: "POST",
    isFileURL: false,
    headers: {
        'content-type': "application/json",
    },
    parameters: {
        foo1: "bar1",
        foo2: "bar2"
    },
    body: {
        foo1: "bar1",
        foo2: "bar2"
    }
};

macs.loadURLRequest (json, function(result) { alert(”Success”); }, function(result) { alert(”Failure”); });
```

### To Run or Build the App

`ionic serve` - to run the app on localhost.

`ionic build --prod` - to build the app.
