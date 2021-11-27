# convert(1)

    convert in.jpg out.png                                     # jpg to png. Supported formats: `identify -list format`

    convert -trim in.jpg out.jpg                               # trim whitespace around image
    convert -trim -fuzz 40% in.jpg out.jpg                     # trim more whitespace around image
    convert -scale 50% in.gif out.png                          # scale down to 50% and convert
    convert -resize 200x100 in.png out.png                     # scale and keep aspect ration (target size might differ)
    convert -crop 500x900+50+100 in.png out.png                # crop from top-left 50x100 with width 500 and height 900
    convert -extent 128x128 -gravity center in.png out.png     # extend image with whitespace and center
    convert -strip in.jpg out.jpg                              # strip metadata

# identify(1)

Describes the format and characteristics of one or more image files

    identify -verbose image.jpg
    identify animated.gif                                      # discover number of frames

# exiftool(1)

    exiftool image.jpg
    exiftool -ext jpg                                         # metedata for all *jpg files in current dir
    exiftool -all= -overwrite_original image.jpg              # remove all metadata of a image file
    exiftool -gps:all= \*.jpg                                  # remove all GPS metadata of *jpg files in current dir
