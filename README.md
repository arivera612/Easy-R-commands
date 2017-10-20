# Easy-R-commands
# Read in files
file1 <- read.delim("file1_list.txt", sep="\t", header=TRUE)
file2 <- read.delim("file2_master.txt", sep="\t", header=TRUE)

#check that files are read in correctly
head(fileX)

#Extract column and save as vector
Vector <- file1$GENE

#check that correct number of genes are in vector
length(Vector)

#look what number the GENE column is in each masterlist
head(file2)

#Actual extraction
Extract <- file2[file2[,7]%in%Vector,]

#Check number of rows
nrow(Extract)

#Write the data into an excel file
write.table(Extract, file="d-3_allcommon_extracted.xls", sep="\t", col.names+TRUE, row.names=FALSE, quote=FALSE)
