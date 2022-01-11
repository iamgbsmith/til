# Log In To Docker Hub From The Command Line

__Category: Docker__

You will need to create an account and log into Docker Hub in order to pull or push images from the Docker Hub registry. 

For security reasons, authentication to Docker Hub should be done using an access token. To generate one, go to https://hub.docker.com/settings/security and open Account Settings from the menu.

Select "Security" then press "New Access Token" specifying a meaningful name for the token. Copy this token to the clipboard.

From a command prompt, log into your Docker Hub account as follows:

```shell
docker login -u username
```

When prompted, enter the value for the access token that was generated in the previous step.

If you need to log out of Docker Hub, issue the following commmand:

```shell
docker logout
```
