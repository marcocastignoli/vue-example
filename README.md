```bash
npm install --save @capacitor/core @capacitor/cli
```
```bash
npx cap init
```

this is needed to compile vue and create the dist folder
```bash
npm run build
```

then edit the capacitor.config.json file and set webDir to "dist"

```bash
npx cap add android
```

```bash
npx cap open android
```