CourseProject3
==============


The idea is to read the test data and training data into two seperate variables and merge them . After that extract only those columns which contains Mean and Standard Deviation and name the columns accordingly . And after that calculate the mean of each column and write it into the result.txt file.


## It is used for reading test data set
q<-read.table("UCI/test/X_test.txt")

##It is used for reading the X traing data set
w<-read.table("UCI/train/X_train.txt")

## It is used for merging the data
e<-rbind(q,w)

##It is used for getting the dimensions of data
dim(e)

##It is used for reading features data
a<-read.table("UCI/features.txt")

##it is used for taking only names 
s<-a[,2]

## It is used for taking only the variables with mean() and std()
d<-grep("mean()|std()",s)

##It is used to extract columns with means and std() from the data set
r<-e[d]

##It is used for assigning names to the columns
names(r)<-s[d]

## It is used to calculate means of variable accross columns
b<-colMeans(r)

##It is used for writing the result into file .
write.table(b,file="result.txt",row.names=FALSE)

