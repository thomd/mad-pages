
    find . -name "import-catalog-201904*" -exec zip import-catalog-201904.zip {} +
    find . -name "import-catalog-201904*" -delete

    ls | grep -o -E \_GBP-.*?_ | sort | uniq

