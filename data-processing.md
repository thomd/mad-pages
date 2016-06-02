# Data Processing

Count number of distinct attributes within a xml file

    grep -o 'xml:lang="[^"]*"' catalog.xml | sort | uniq -c
