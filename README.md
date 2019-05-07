# HPOSim

R version: 64bit 3.5.2

1. import AnnotationDbi:

source("http://bioconductor.org/biocLite.R")

biocLite("AnnotationDbi")

2. library(igraph)

3. library(HPO.db)

4. library(HPOSim)

Sometimes error "there is no package called 'Rcpp'" will occur, to address this, install.packages('Rcpp'), then library('Rcpp')


First setup: IC<-get("termIC",envir=HPOSimEnv)

Sometimes error "termIC" not found will occur. To solve this, just run some sample code to initiate HPOSim package, such as:

 terms<-c("HP:0000002","HP:0000012")
 
 result<-getTerm(terms)
 
 print(result)



Test 1: calcTermSim("HP:0003159",i, method = "Wang", IC, verbose = FALSE)

Test 2:
anno1<-c("HP:0000118", "HP:0000152", "HP:0000234", "HP:0000271")

anno2<-c("HP:0000152", "HP:0000234", "HP:0000271")

getTermListSim(anno1, anno2, combinemethod="funSimMax", method="Wang", IC, verbose=FALSE)
