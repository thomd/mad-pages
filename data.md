# File Processing

Search-Replace in all JS files:

    rg -l -t js foo | xargs sed -i '' 's/foo/bar/g'

Grep PATTER within a large list of log files

    while read f; do grep -E \<pattern> $f; done \< \<(find . -name "*.log")  
    rg -t log \<pattern>

List Distribution of File Extensions in Current Directory:

    while read file; do echo ${file##\*.}; done \< \<(find . -type f) | sort | uniq -c
    fd -t f | sed 's/.*\.//' | sort | uniq -c

Copy amount of random jpg images larger than 256px in width and height from source- into target-folder:

    while read f; do cp $f target; done \< \<(fd -e jpg . source -x identify | awk '{gsub("x"," ",$3); print $3 " " $1}' | awk '{if($1 >= 256 && $2 >= 256){print $3}}' | shuf -n 4500)

Download fake-face-images with progress bar

    for i in {1..10}; do wget --quiet https://thispersondoesnotexist.com/image -O "face-${i}.jpg"; echo $i; done | tqdm --total 10

Rename Files with Counter

    n=1; for f in \*.jpg; do mv "$f" "$(printf "foo_%02i.jpg" "$n")"; ((n++)); done

# XML

Count number of distinct attributes within a XML file:

    grep -o 'xml:lang="[^"]*"' catalog.xml | sort | uniq -c

Format multiple XML files:

    for f in \*; do g=\`echo $f | sed 's/_\{.*\}//'`; xmllint --format $f > $g; rm $f; done

Get product-ids of products with a specific attribute:

    awk '/product-id/{p=$0} /attribute/{print p}' catalog.xml
    awk 'BEGIN{p=0;a=0} /product-id=".*"/{p=1;gsub("(product-id=\")|(\")","",$0);id=$0} /attribute/{a=1} /\/product/{if(p==1&&a==1){print id};p=0;a=0}' catalog.xml

Get lengths of display-name values:

     awk '/display-name/{gsub(" *<[^>]+>","",$0); print length(), $0}' catalog.xml | sort | uniq | sort -n

Get text-node `bar` of `\<foo>bar\</foo>` tag:

    grep foo file.xml | perl -pe 's/ \*\<.\*?>//g'

Extract values of an attribute from an XML:

    grep customer-no file.xml | perl -pe 's/.\*(CA\d+).\*/\1/g'
    grep customer-no \*.xml | perl -pe 's/.\*customer-no="(.\*?)".\*/\1/g' | sort -n
    grep -o 'CA[0-9]\{8\}' file.xml

Replace all prices in a price-book with '7.77':

    cat pricebooks.xml | perl -pe 's/(\<amount quantity="\d">).*(\<\/amount>)/${1}7.77${2}/g' \
        | sed /parent/d \
        | perl -pe 's/(pricebook-id=").*"/${1}gbp-m-777-prices"/g' \
        | perl -pe 's/(\<display-name.\*>).*</${1}GBP 7.77 Prices</g'

# ISML

Find large \<isset> tags

    fd -e isml -X grep -oh -e "\<isset.*/>"
