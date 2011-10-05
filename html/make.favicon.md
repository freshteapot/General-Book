#How to make a favicon.ico file.

You do need imagemagick for this.

FILENAME = your file you want to turn into an icon.
```
convert FILENAME 256x256 -transparent white favicon-256.png
convert favicon-256.png -resize 16x16 favicon-16.png
convert favicon-256.png -resize 32x32 favicon-32.png
convert favicon-256.png -resize 64x64 favicon-64.png
convert favicon-256.png -resize 128x128 favicon-128.png
convert favicon-16.png favicon-32.png favicon-64.png favicon-128.png favicon-256.png -colors 256 favicon.ico
```

Full credit must be given to Daniel A. Bergamini. His website below is where I have reduced the commands into one easy block to copy and paste.

##Links
* http://bergamini.org/computers/creating-favicon.ico-icon-files-with-imagemagick-convert.html
* http://www.imagemagick.org/Usage/
