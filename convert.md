# convert(1)

    convert -trim old.jpg new.jpg                     # trim whitespace around image
    convert -trim -fuzz 40% old.jpg new.jpg           # trim more whitespace around image

    convert old.jpg new.pdf                           # jpg to pdf. supported formats: `identify -list format`
    convert old.jpg new.png                           # jpg to png

    convert -scale 50% old.gif new.png                # scale down to 50% and convert
    convert -crop 500x900+50+100 old.png new.png      # crop from top-left 50x100 with width 500 and height 900

    convert -strip with.jpg without.jpg               # strip metadata. verify with `exiftool`

