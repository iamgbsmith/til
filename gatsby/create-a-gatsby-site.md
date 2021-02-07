# Create A Gatsby Site

__Category: Gatsby__

### Start development mode

Install Gatsby CLI:

```shell
npm install -g gatsby-cli
```

Create the site using a template. the following example creates a site called `your-cool-blog` using the template at https://github.com/gatsbyjs/gatsby-starter-blog:

```shell
gatsby new your-cool-blog https://github.com/gatsbyjs/gatsby-starter-blog
```

Change to the new directory and start the development server:

```shell
cd your-cool-blog
gatsby develop
```

Browse to the site at http://localhost:8000

Any changes made to the source code will be dynamically reloaded in your browser.

### Build for production

Stop the development server.

Create static HTML content with the following command:

```shell
gatsby build
```

The output from this is a production build of your site with static files generated in the `public` directory.

View the production server locally. Run the following command:

```
gatsby serve
```

Once the server starts you can view your site at http://localhost:9000