Provided files are split into lines. Lines that start with tabulation (`\t`) character are `value lines`, lines that don't are `key lines`.

Key lines are read until `//` or end of the line, trailing whitespaces are trimmed, resulting string is then considered a `key` for the following lines, until another key or end of file are found.

Value lines have first tabulation removed, joined with newline (`\n`), then passed into resulting map with further modifications.

## Example
**Source file**:
```
key0 // comment
	value

key1
	another value

k ey-?2  // another comment
	multiline
	value
```
is parsed as three map entries, with keys `key0`, `key1`, and `k ey-?2`.