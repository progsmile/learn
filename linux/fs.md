Find text in files
- `grep -Ri "text-to-find-here" ./`

List files that contains text
- `grep -Ril "text-to-find-here" ./`

Show number of string occurrences in file
- `grep -o "string_to_find" filename | wc -l`

Check sha256
- `sha256sum filename.xlsx`

Determine type of file
- `file filename.xlsx`

Copy recursive directories and files preserving mode, ownership, timestamps (--preserve)
- `cp -pr ./dir1 ./dir2`

