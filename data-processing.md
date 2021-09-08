
# Data Processing

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

Replace all prices in a pricebook:

    cat pricebooks.xml | perl -pe 's/(<amount quantity="\d">).*(<\/amount>)/${1}7.77${2}/g' > new_pricebook.xml
