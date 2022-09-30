# File Type

    file file.txt

# File Format

  DOS line endings: `0D0A`
  UNIX line endings: `0A`

    vim
    :set ff?

# File Encoding

    vim file.txt
    :set fenc?                                       # detemine file encoding
    :set fenc=utf-8 	                               # change file encoding to UTF-8
    :set fenc=iso-8859-1 	                       # change file encoding to ISO-8859-1

    :set bomb?                                       # determine byte-order-mark

    file -I file.txt                                 # determine encoding

    iconv -f ISO-8859-1 -t UTF-8 file.txt            # covert file from latin-1 to utf-8


