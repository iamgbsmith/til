# Create A React Progressive Web App

__Category: React__

### Create the app

Create a Progressive Web App (PWA) in React from the command line using the TypeScript template as follows:

```shell
npx create-react-app my-project --template cra-template-pwa-typescript
cd my-project
```

Install package dependencies:
```
yarn
```

In the `index.tsx` file change the line `serviceWorkerRegistration.unregister()` to `serviceWorkerRegistration.register()` to opt in using the service worker.

### Create the icons

Ensure you create icons specific to your application in the `/public` folder and they are loaded in `/public/manifest.json`. Configure other values such as the application name by editing the manifest file.

### Run the app

Progressive Web Apps can only be installed if they are being served on localhost or publicly over HTTPS.

Build the app:

```
yarn build
```

Run the app locally on port 4000 using `serve`:

```
serve -s build -l 4000
```

Browse to the application at http://localhost:4000

If using Brave or Chrome you should see an icon in the right hand side of the browser address bar which says "Install [Name of App]". Click on this to download and install the app.

__Note:__ Safari and Firefox might not show the icon to install the app. On iOS Safari, you will need to follow instructions for [adding an app to the home screen](https://support.apple.com/en-nz/guide/shortcuts/apd735880972/ios).

See [Making a Progressive Web App](https://create-react-app.dev/docs/making-a-progressive-web-app) for more details.
