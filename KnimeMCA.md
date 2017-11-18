This procedure is used for dimentionality reduction in preparation for decision tree usage. 
The primary usage for this code is the pre-post CANS scores which result in (NoNeed, PresUnresolved, PresResolved and Discovered)
The One-to-Many node creates 4 dummy variables (one for each result) for each CANS item. 
In addition you may want to use the Low Vairance Filter node to eliminate columns with little variance.

**Assumptions:**

Wihtin Knime the variables have been transormed into dummy variables using the One-to-Many node. 

**Possible Errors:**

Error: argument to 'which' is not logical - By default using the One-to-Many node is going to produce dummy varialbes with a 1 or a 0. These need to be converted using the Number to String node into categorical variables.

**Cheat Sheet for Output Types**

   name              description                       
1. "$eig"            "eigenvalues"                     
2. "$var"            "results for the variables"       
3. "$var$coord"      "coord. of the categories"        
4. "$var$cos2"       "cos2 for the categories"         
5. "$var$contrib"    "contributions of the categories" 
6. "$var$v.test"     "v-test for the categories"       
7. "$ind"            "results for the individuals"     
8. "$ind$coord"      "coord. for the individuals"      
9. "$ind$cos2"       "cos2 for the individuals"        
10. "$ind$contrib"    "contributions of the individuals"
11. "$call"           "intermediate results"            
12. "$call$marge.col" "weights of columns"              
13. "$call$marge.li"  "weights of rows"       

**Code for Factor Exploration**
```R
knime.out <- knime.in
x<-cbind(knime.in)
library(FactoMineR)
mca1<-MCA(x, ncp=6, graph=FALSE)
knime.out<-as.data.frame(mca1$var$contrib)
```

**Code for Scoring**
```R
knime.out <- knime.in
x<-cbind(knime.in)
library(FactoMineR)
mca1<-MCA(x, ncp=6, graph=FALSE)
knime.out<-as.data.frame(mca1$ind$contrib)
```
