# Data Processing

Count number of distinct attributes within a xml file

    grep -o 'xml:lang="[^"]*"' catalog.xml | sort | uniq -c

Format multiple xml files

    for f in *; do g=`echo $f | sed s/_\{.*\}//`; xmllint --format $f > $g; rm $f; done

Get product-ids of products with a specific attribute

    awk '/product-id/{p=$0} /attribute/{print p}' catalog.xml
    awk 'BEGIN{p=0;a=0} /product-id=".*"/{p=1;gsub("(product-id=\")|(\")","",$0);id=$0} /attribute/{a=1} /\/product/{if(p==1&&a==1){print id};p=0;a=0}' catalog.xml
