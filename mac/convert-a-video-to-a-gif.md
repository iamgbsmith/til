# Convert A Video To A GIF

__Category: Mac__

You can convert from MP4 or MOV format to an animated GIF on macOS using `ffmpeg` and `Gifsicle`. You may find this useful if you need to showcase an application on a web site or GitHub repo. 

This TIL assumes you have already installed `brew`.

Install dependencies using brew:

```shell
brew install ffmpeg
brew install gifsicle
```

Convert the movie to an animated GIF as follows:

```shell
ffmpeg -i your-movie.mov -pix_fmt rgb8 -r 10 animated-output.gif 
```

Reduce the size and optimise the output:

```shell
gifsicle -O3 animated-output.gif -o animated-output.gif
```

See [ffmpeg](https://www.ffmpeg.org) and [gifsicle](https://www.lcdf.org/gifsicle) for more details.
