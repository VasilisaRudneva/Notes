# Notes

## Perl
###Fix text files between Windows and Mac OS in one line
```
perl -pi -e 's/\r\n|\n|\r/\n/g'
```

## R
### How to draw the boxplot with significant level?
```
pp <- ggplot(mtcars, aes(factor(cyl), mpg)) + geom_boxplot()
df1 <- data.frame(a = c(1, 1:3,3), b = c(39, 40, 40, 40, 39))
df2 <- data.frame(a = c(1, 1,2, 2), b = c(35, 36, 36, 35))
df3 <- data.frame(a = c(2, 2, 3, 3), b = c(24, 25, 25, 24))

pp + geom_line(data = df1, aes(x = a, y = b)) + annotate("text", x = 2, y = 42, label = "*", size = 8) +
     geom_line(data = df2, aes(x = a, y = b)) + annotate("text", x = 1.5, y = 38, label = "**", size = 8) +
     geom_line(data = df3, aes(x = a, y = b)) + annotate("text", x = 2.5, y = 27, label = "n.s.", size = 8)
```
