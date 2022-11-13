# vd(1)

## Commands

    F      # frequency table
    I      # descriptive statistics
    C      # open columns sheet
    S      # open sheets sheet


    _ toggle column width
- hide column
gv unhide all columns
[ sort ascending
] sort descending
/ / g/ search in current / all column
s / u select / unselect a row
| / g| select all matching rows of current / all column/s
, select all rows where the current column matches the current cell
i create an increment column
! / z! make / unmake current column a key column
: create new column by splitting current column on regex
" create new sheet of selected rows
Ctrl ^ toggle between current and previous sheet
H, J, K, L move left, up, down, right
e / ge (in memory) edit current cell / selected cells
Enter finish editing a cell
Ctrl c cancel editing a cell
Ctrl r reload sheet (memory undo)
^ rename current column

Ctrl e examine the latest general error
g Ctrl e examine all general errors encountered

    #      # set column type integer
% set column type float
$ set column type currency
@ set column type date
~ set column type text
