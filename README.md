# ImageMagick Cheat Sheet
 <img src="[https://github.com/sh4de-c4t/sh4de-c4t/blob/main/KLONDAK%20-FINAL.gif](https://github.com/sh4de-c4t/ImageMagick-Cheat-Sheet/blob/main/imagemagick%20cheat-sheet.png)" width="400px" />
### Create thumbnail:

```
convert -geometry 100x100 -quality 100 orgfilename.jpg thumbfilename.jpg
```

### Rotate an image:

```
convert orgfilename.jpg -rotate 60 rotated60.jpg
```

### Crop an image:

```
convert orgfilename.jpg -crop 128×128+50+50 cropped.jpg
```

### Crop an image for several files:

```bash
for file in *.png; do convert -crop 863x675+227+51 "$file" "x6/$file"; done 
```

### Convert a directory of PNG images to GIF:

```
mogrify -format gif *.png 
mogrify -format webp *.png 
```

### Watermarking with text:

```bash
convert orgfilename.jpg -font Arial -pointsize 20 -draw "gravity south fill black text 0,12 'Watermark' fill white text 1,11 'Watermark' " wmark_text_drawn.jpg
```

### Convert PDF to PNG:

```bash
convert pdffile.pdf -colorspace RGB -resample 72×72 -units PixelsPerInch -quality 90 -resize 500×500 -size 500×500 pngfile.png
```

### Convert JPG to PDF:

```bash
convert *.jpg output.pdf 
convert input.png PNG24:output.png
```

### For several images to a single PDF: (yeah, not magick)

```bash
img2pdf --out z2.pdf *.png
```

### Compression for PNG:

```bash
pngquant *.png
```

### PDF too big (from jpg):

```bash
convert -quality 60 *.jpg output.pdf
```

### Resize an image:

```bash
convert image.jpg -resize 800 image.png
mogrify -path xx -resize 800 *.jpg
```

### Compare two images:

```bash
compare image1 image2 -compose src diff.png
compare PC-200617-1248-30.pdf PC-270717-1119-53.pdf diff.pdf (pdf) 
```

### Append two images:

```bash
convert image1.jpg image2.jpg -append result.jpg 
```

### To verify ImageMagick is working properly, type the following in a Windows Command Prompt window:

```bash
convert logo: logo.gif 
identify logo.gif
imdisplay
```

### To see details of the image: (information)

```bash
identify image.ext 
identify dp1.jpg
magick identify image
magick identify -verbose r00.png
```

### Invert colors:

```bash
convert input.png -channel RGB -negate output.png 
```

### Black & White colors:

```bash
convert input.png -colorspace Gray output.png 
```

### Problems with spaces and hyphens in filenames:

```bash
find . -name "* *" -type f | rename 's/ /_/g'
```
