# Build For Production

__Category: Nodejs__

Package dependencies in `yarn.lock` or `package-lock.json` are sometimes updated when running either `yarn install` or `npm install`. For production builds, this can cause regression problems and have unintended consequences on application behaviour.

When building Node applications for production on a continuous integation platform you should use a frozen lockfile. 

If building with `npm`, use the following command (clean install):

```shell
npm ci --only=prod
```

If building with `yarn`, use the following command (this will not generate a `yarn.lock` lockfile and fail if any package update is required):

```shell
yarn install --frozen-lockfile --production
```

__Note:__ Building for production will also remove devDependencies.
