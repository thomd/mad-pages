# date(1)

Special Dates

    date +%V                                                          # calendar-week (KW)
    date +%s                                                          # time since UNIX EPOCH

Date Diffs

    date -v -2d                                                       # date two days ago
    date -v +75d                                                      # date in 75 days
    date -v +75d "+%d.%m.%Y"                                          # date in 75 days
    while read p; do date -v -${p}d; done < <(seq 10)                 # date of the 10 past days

Transformations

    date -j -f %s 1583429905 +%Y-%m-%d_%H:%M:%S                       # transform unix timestamp to readable date-time
    date -j -f "%Y-%m-%d %H:%M:%S" "2020-03-05 18:38:25" +"%s"        # transform readable date-time to unix-timestamp
