### Assignment 7

```markdown
#set up
databank<-read.table("C:\\Users\\selin\\Desktop\\zhanj392_crash.txt",sep=",",header=T,na.strings=c("","NA"))
crash<-read.table("C:\\Users\\selin\\Desktop\\zhanj392_crash.txt",sep=",",header=T,na.strings=c("","NA"))

#1
size<-crash$size
size<-size[!is.na(size)]
table(size)
med<-crash$med
med<-med[!is.na(med)]
lnhic<-log(crash$hic)
subset=(size == "comp" | size == "med")
t.test(lnhic~size,data=crash,alt="two.sided",conf.level=0.92,var.equal=FALSE,na.action="na.omit",subset=(size=="comp"|size=="med"))
#pvalue=0.1446,confidence interval (a,b) = -0.025976,0.28173802

#4
table<-read.table("C:\\Users\\selin\\Desktop\\3y_assignment_7_that_xy_bullcrap_problem.txt",sep=",",header=T,na.strings=c("","NA"))
values<-table
x<-table$x
y<-table$y
t.test(x~values,data=table,alt="two.sided",conf.level=.01,var.equal=FALSE,na.action="na.omit")
reg<-lm(data=values)
summary(reg)
anova(reg)
plot(reg,2,pch=19,col="blue")
#^^for reference cus I didnt get it right in the end :(

#5
databank<-read.table("C:\\Users\\selin\\Desktop\\zhanj392_crash.txt",sep=",",header=T,na.strings=c("","NA"))
crash<-read.table("C:\\Users\\selin\\Desktop\\zhanj392_crash.txt",sep=",",header=T,na.strings=c("","NA"))
lnhic<-log(crash$hic)
mean(lnhic,na.rm=T)
wt<-crash$wt
mean(wt,na.rm=T)
reg<-lm(lnhic~wt,data=crash)
summary(reg)
anova(reg)
#b0=6.221, b1=0.0001564, pvalue = 0.000482
#more severe for heavier vehicles because b1 is positive

#8

```

