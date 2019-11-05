
# Photos Management

Sort photos based on creation date into folders `../2019/2019-12-06/...`

    while IFS= read -r -d '' F
    do
      D=`exiftool "$F" | grep "Create Date" | awk '{print $4}' | tr ':' '-'`
      DD=`echo "$D" | cut -c 1-4`
      echo "$DD $D $F"
      mkdir -p "../$DD/$D"
      FF=`basename "$F" | tr -s ' ' '-'`
      cp "$F" "../$DD/$D/$FF"
    done < <(find . -type f -iname '*.jpg' -print0)
