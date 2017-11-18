Performs Factor Analysis within Knime using the Psych Library and Factanal

```R
knime.out <- knime.in
x<-cbind(knime.in)
##cor(x)
##library(psych);vss(x)
##pca1<-princomp(x, scores=TRUE, cor=TRUE);loadings(pca1);plot(pca1); abline(h=1)
factors<-factanal(x, factor=5, rotation="varimax", scores="regression")
##Use the code below to see factor loadings as a table to name the factors.
##knime.out<-as.data.frame(unclass(factors$loadings))

knime.out<-factors$scores
```
