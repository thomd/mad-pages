# PDF

## Extract text from a PDF file

    magick -density 300 file.pdf -quality 100 file.jpg
    tesseract file.jpg - --oem 1 -l deu > file.txt
