# Notes

## Fix text files between Windows and Mac OS in one line
```
perl -pi -e 's/\r\n|\n|\r/\n/g'
```
