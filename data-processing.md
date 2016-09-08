# Data Processing

Count number of distinct attributes within a xml file

    grep -o 'xml:lang="[^"]*"' catalog.xml | sort | uniq -c

Format multiple xml files

    for f in *; do g=`echo $f | sed s/_\{.*\}//`; xmllint --format $f > $g; rm $f; done
