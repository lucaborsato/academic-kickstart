---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "How To: Image Magick"
subtitle: "Very brief usage of Image Magick and pdf converting issue policy."
summary: "Very brief usage of Image Magick and pdf converting issue policy."
authors: ["admin"]
tags: ["HowTo", "Linx", "imagemagick"]
categories: ["HowTo"]
date: 2020-08-09T15:22:25+02:00
lastmod: 2020-08-09T15:22:25+02:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---


Convert and resize to maximum heightxwidth:  

```bash
convert -resize '3072x3072' input_image output_image
```

Create serie of image in one single image:  
- automatic (1 row)
  
  ```bash
  montage image_1 image_2 ... output_image
  ```

- define 7row x 7col, each image has a shadow, each image is separated by 5px heigh and 5px widht, background is gray

  ```bash
  montage image_1 image_2 ... -tile 7x7 -shadow -geometry +5+5 -background gray output_image
  ```

## Converting PNG/JPG to PDF

If you try to convert an image, such as a png o jpg/jpeg, to a pdf it is likely that you will get something like this:

```bash
convert IMAGE.png IMAGE.pdf
convert-im6.q16: not authorized `IMAGE.pdf' @ error/constitute.c/WriteImage/1037.
```

This is due to a policy issue withing `ghostcript` and you could not convert to pdf/ps/etc.
There is a way to solve it but it could put your computer at risk.  
Please read this two post about it (how to solve it and why):  

- [Trouble with batch conversion of .png to .pdf using convert](https://askubuntu.com/questions/1081895/trouble-with-batch-conversion-of-png-to-pdf-using-convert)  
- [Solution to ImageMagick "not authorized" PDF Error](https://cromwell-intl.com/open-source/pdf-not-authorized.html)  
