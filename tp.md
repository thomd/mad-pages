
zip away imported catalog files

    find . -name "import-catalog-201904\*" -exec zip import-catalog-201904.zip {} +
    find . -name "import-catalog-201904\*" -delete

which masters were changed most?

    find . -name "\*.xml" | grep mastercatalog | perl -pe 's/.\*\_mastercatalog\_(.\*?)\_.\*/\1/g' | sort | uniq -c | sort -n

what has been changed of a particular master over time?

    find . -name "\*.xml" | grep mastercatalog | grep \_157425\_ | sort | xargs -n 2 icdiff | less
