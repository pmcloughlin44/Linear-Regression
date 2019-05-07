
#Linear regression

myurl<-"https://docs.google.com/spreadsheets/d/e/2PACX-1vTEZDgR0YJK_iuBOrLyRLOx_pZSh03sayLx2eOoZp2BylkFKYBliHnZX3t-2Ny4YSPtL7iDiBvDPn3W/pub?output=csv"
scores<-read.csv(url(myurl) ) 
scores
final<-scores$FINAL/2
final
plot(scores$EXAM1, final ,xlab="Exam 1 Scores", ylab="Final exam scores", main="linear regression line")
mean.Exam1<-mean(scores$EXAM1)
abline(h=mean.Exam1)
model1<-lm(scores$EXAM1~ final, data=scores)  
abline(model1, col="red")
cor(  scores$EXAM1, final)
summary.lm(model1)

#Multiple Linear Regression

model2<-lm(final~scores$EXAM1+scores$EXAM2+ scores$EXAM3,data=scores)
summary(model2)



