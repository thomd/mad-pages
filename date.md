# date(1)

Special Dates

    date +%V                         # calendar-week (KW)
    date +%s                         # time since UNIX EPOCH

Date Diffs

    date -v -2d                      # date two days ago
    date -v +75d                     # date in 75 days
    date -v +75d "+%d.%m.%Y"         # date in 75 days
