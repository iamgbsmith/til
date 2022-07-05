# Convert HEIC Images To Another Format

__Category: Mac__

The Preview application can be used to convert HEIC images from one format to another.

You can also convert images to JPEG or PNG format from the command line using the ImageMagick `Mogrify` utility.

This TIL assumes you have already installed `brew`.

Install dependencies using brew:

```shell
brew install imagemagick
```

Convert all HEIC images in the current directory to JPG/JPEG as follows:

```shell
mogrify -format jpg *.heic
```

Change the target image format to match your needs.
