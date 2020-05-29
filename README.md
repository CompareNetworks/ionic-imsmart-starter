# ionic-imsmart-starter
 
## To Start an Ionic Project for imSMART

### Install the Latest Version of Ionic

```console
npm i -g @ionic/cli
```

### Intiate the Ionic Project
Initiate the Ionic project. Below names the project "ionic-imsmart" and sets the type to "tabs"

```console
ionic start ionic-imsmart tabs  --type=angular
```

### Install the imSMART NPM Module
You will need access to the private imSMART NPM account to install the imsmart module

```console
npm install @comparenetworks/imsmart-web --save
```

### Update TSConfig to use Angular 8
The current version of the NPM module (6.0.1) does not support Ivy. In the tsconfig.json at the base of the directory created Add the "enableIvy: false property (leave any other properties)

```json
"angularCompilerOptions": {
    "enableIvy": false
  }
```
