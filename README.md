# Notes

## Perl
### Fix text files between Windows and Mac OS
```
perl -pi -e 's/\r\n|\n|\r/\n/g'
```

## R
### Boxplot with significance level
```
pp <- ggplot(mtcars, aes(factor(cyl), mpg)) + geom_boxplot()
df1 <- data.frame(a = c(1, 1:3,3), b = c(39, 40, 40, 40, 39))
df2 <- data.frame(a = c(1, 1,2, 2), b = c(35, 36, 36, 35))
df3 <- data.frame(a = c(2, 2, 3, 3), b = c(24, 25, 25, 24))

pp + geom_line(data = df1, aes(x = a, y = b)) + annotate("text", x = 2, y = 42, label = "*", size = 8) +
     geom_line(data = df2, aes(x = a, y = b)) + annotate("text", x = 1.5, y = 38, label = "**", size = 8) +
     geom_line(data = df3, aes(x = a, y = b)) + annotate("text", x = 2.5, y = 27, label = "n.s.", size = 8)
```
### Q-Q Plot
```
log_obs_pvalues=data2$V2
log_obs_pvalues = sort(log_obs_pvalues)
uni_pvalues=runif(length(data2$V2))
log_uni_pvalues= -log10(uni_pvalues)
log_uni_pvalues = sort(log_uni_pvalues)
plot (log_uni_pvalues,log_obs_pvalues, xlab=expression(Theoretical~~-log[10](italic(p))), ylab= expression(Observed~~-log[10](italic(p))), main="QQ-plot")
abline(0,1, col="red")
hist(data.tmp2$adj.P.Val)
```
