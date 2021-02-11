# Rotate An Image

__Category: Mac__

Preview only allows for rotating of images by 90 degrees. In some situations however, you might need to rotate an image by a different number of degrees.

To rotate an image from the command line in degrees other than 90, issue the following command:

```shell
sips -r 41 --padColor FFFFFF your-image.png 
```

In the above example:

* `41` is the degrees to rotate by
* `--padColor` specifies the colour for "filling in" the empty space (in this case, with FFFFFF which is the hex colour code for white)

__Note:__ When rotating a PNG file, the alpha channel will be retained.