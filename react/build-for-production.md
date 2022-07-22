# Build For Production

__Category: React__

You can create a production build for a React application using:

```shell
yarn run build
``` 

The output of this will be static content generated in the `/build` directory with CSS, JavaScript, and media files contained in `/build/static`.

For optimal performance, specify `Cache-Control: max-age=31536000` (one year) for content served in `build/static` and `Cache-Control: no-cache` for everything else. A cache expiry of one year will not cause any issues as filenames contain unique hashes.

Deploy the content in `/build` to a web server or run locally using `serve` as follows:

```shell
serve -s build
```
