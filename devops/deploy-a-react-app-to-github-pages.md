# Deploy A React App To GitHub Pages

__Category: DevOps__

You can deploy a static website or app to GitHub pages. 

This TIL will add dependencies to a React project so that it can be built and deployed to GitHub pages.

### Add package dependencies

Add the required dependencies:

```shell
yarn add --dev gh-pages
```

Update scripts in `package.json` to add the following:

```json
"predeploy": "npm run build",
"deploy": "gh-pages -d build"
```

Add a property called `homepage` to `package.json`, changing the values for "username" and "repository-name" to match your account and the repository.

```json
"homepage": "https://{username}.github.io/{repository-name}"
```

### Build the app

Commit all changes and push them to the remote repo.

Run the `deploy` script from your command line (this creates a `gh-pages` branch in the remote repo):

```shell
yarn deploy
```

### Deploy the app to GitHub Pages

Log into GitHub and select Settings -> Pages for your repository.

From the Branch drop-down, select "gh-pages" and press Save.

Your project site will be built from the `gh-pages` branch.
 
Visit the site at: https://{username}.github.io/{repository-name}
