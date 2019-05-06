# Linear-Regression

myurl<-"https://docs.google.com/spreadsheets/d/e/2PACX-1vTEZDgR0YJK_iuBOrLyRLOx_pZSh03sayLx2eOoZp2BylkFKYBliHnZX3t-2Ny4YSPtL7iDiBvDPn3W/pub?output=csv"
scores<-read.csv(url(myurl) ) 
scores
plot(scores$EXAM1, scores$EXAM2, xlab="Exam 1 Scores", ylab="Exam 2 Scores", main="linear regression line")
mean.Exam1<-mean(scores$EXAM1)
abline(h=mean.Exam1)
model1<-lm(scores$EXAM1~ scores$EXAM2, data=scores)  
abline(model1, col="red")
summary.lm(model1)
