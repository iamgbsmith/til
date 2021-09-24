# Optimise For Performance

__Category: Nodejs__

You can optimise Nodejs server performance and security in production by using the `env NODE_ENV=production` environment variable.
 
Using this setting in Express will cache view templates and CSS files generated from CSS extensions, and will generate less verbose error messages.
 
If you want to start your server using this setting, use the following command:
 
```shell
NODE_ENV=production node server.js
```
 
In a Dockerfile, include the directive `ENV NODE_ENV production` if you are building production images:
 
```shell
FROM node:lts-alpine@sha256:b2da3316acdc2bec442190a1fe10dc094e7ba4121d029cb32075ff59bb27390a
ENV NODE_ENV production
WORKDIR /usr/src/app
COPY . /usr/src/app
RUN npm ci --only=production
CMD "npm" "start"
```
 
Alternatively, set as an environment variable which can be read in by the node process or a container orchestration engine.
 
On Windows, to set as an environment variable:
 
```command
SET NODE_ENV=production
```
 
On Linux, to set as an environment variable:
 
```shell
export NODE_ENV=production
```
 
See [Best Practice Performance in Express](https://expressjs.com/en/advanced/best-practice-performance.html#set-node_env-to-production) for more details.
 