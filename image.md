# convert(1)

    convert -trim old.jpg new.jpg                        # trim whitespace around image
    convert -trim -fuzz 40% old.jpg new.jpg              # trim more whitespace around image

    convert old.jpg new.pdf                              # jpg to pdf. supported formats: `identify -list format`
    convert old.jpg new.png                              # jpg to png

    convert -scale 50% old.gif new.png                   # scale down to 50% and convert
    convert -crop 500x900+50+100 old.png new.png         # crop from top-left 50x100 with width 500 and height 900

    convert -strip with.jpg without.jpg                  # strip metadata. verify with `exiftool`

# identify(1)

Describes the format and characteristics of one or more image files

    identify -verbose image.jpg
    identify animated.gif                                # discover number of frames
    
# exiftool(1)

    exiftool image.jpg
    exiftool -ext jpg                                    # metedata for all *jpg files in current dir
    exiftool -all= -overwrite_original image.jpg         # remove all metadata of a image file
    exiftool -gps:all= \*.jpg                             # remove all GPS metadata of *jpg files in current dir
