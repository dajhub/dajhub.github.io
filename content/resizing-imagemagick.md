+++
title =  "Resizing Images with ImageMagick"
date =   "2021-02-15"
description = "Using ImageMagick to modify image formats via the command line."
[taxonomies]
tags = ["software"]
+++

ImageMagick is free and open-source software which allows you to use the command line to convert and modify images in many formats including GIF, JPEG, and PNG. Using the terminal to manipulate images is, on the whole, straightforward and can save a lot of time. 

## Installing

In Fedora you will first need to install ImageMagick:

```bash
$ sudo dnf install ImageMagick
```

In Ubuntu the commands are:

```bash
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install imagemagick
```

In Arch:

```bash
$ sudo pacman -S imagemagick
```
## The Commands

There are a range of different activities you can do using ImageMagick. Below are two commands which I use regularly.

### Converting an Image to a Different Format

You may, for example, have an image which you want to convert from a png to jpg format. To do this make sure you are in the directory where your file is.  If the picture is in the folder Pictures then in your terminal type, `cd Pictures`. Once in the correct folder type into the terminal:

```bash
$ convert forest.png forest.jpg
```

### Resizing an Image

The convert command can also be used to quickly resize an image. I often use this to resize images for my screen size or my blog.  The following command gets ImageMagick to resize an image to 1366 pixels in width and 768 pixels in height:

```bash
convert forest.jpg -resize 1366x768 forest.jpg
```

### Additional Commands
To find out the other things you can do with the package visit the ImageMagicks [**github page**](https://github.com/ImageMagick/ImageMagick#features-and-capabilities).
