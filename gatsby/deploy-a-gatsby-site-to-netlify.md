# Deploy A Gatsby Site To Netlify

__Category: Gatsby__

### What is Netlify?

Netlify is a servless platform capable of hosting web sites developed using a variety of frameworks including Jamstack, Gatsby, React, Vue, Angular, Next.js, Drupal, and Wordpress.  Websites can be configured with free SSL certificates from Lets Encrypt.

This TIL will deploy a Gatsby site to Netlify from a GitHub repository and configure it for use with a custom domain. The steps outlined here assume you have registered an account with Netlify and have full control of DNS configuration for your domain.

### Configure the project

Add `gatsby-cli` to your project:

```shell
yarn add gatsby-cli
```

### Connect to Netlify

Log into the Netlify console and select the option __New site from Git__. 

From the Create a new site page, select GitHub.

Press __Authorise application__ for Netlify when prompted at the popup window.

### Select your repository

Select the specific repository which contains your Gatsby site then press __Install__.

### Configure build options

Select the appropriate settings

* Branch to deploy = `main`
* Build command = `yarn build`
* Publish directory = `/public`

Press the __Deploy site__ button and wait for the build to finish deploying your site.

The site should be accessible at https://some-random-site.netlify.app/

### Use a custom domain

Enter the name of your custom domain when prompted.

You may need to verify DNS configuration by logging into your domain host and configuring a CNAME entry for www to resolve to netify.

For example:

www CNAME some-random-site.netlify.app

Changes may take 24 hours for DNS records to propagate globally.

### Enable HTTPS

Select HTTPS under the Domain Management menu. Under the SSL/TLS certificate option, press the Verify DNS button. Assuming you have configured your CNAME correctly, you will see a message saying DNS verification was successful. Enabling SSL may take up to 24 hours to become effective.

### Automated deployments

Each time you commit and push changes for your site to GitHub, a new build will be triggered on Netlify. As soon as the build finishes, changes should be live on the internet.
