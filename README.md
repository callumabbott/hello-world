
########## DATA TYPES AND STRUCTURES ##########

# basic math operations and strings
1 + 4
test # this is a comment; instruct students to comment their code
1 +   4
1 + # code spread over multiple lines
  4
a <- 3
b <- 1 + 4
a + b
a + b == 8
a + b == 7
c <- a + b == 7
c
a * b
a / b
a - b
a^b
sqrt(b)
log(b)
class(b) # add 'numeric' and 'integer' to whiteboard
class(c) # add 'logical' to whiteboard

# character strings
c <- "abcd"
d <- "efg"
class(c) # add 'character' to whiteboard
paste(c, d)
paste(c, d, c, sep = ";")
e <- paste(c,d,c, "\n\n", "hello", "\n\n", sep="")
e
print(e) # same result
cat(e) # proper line breaks

# the workspace
getwd()
old.wd <- getwd()
setwd("/home/philip/Desktop/") # use tab key to complete path
getwd()
setwd(old.wd)
getwd()
dir()
ls()
rm(b)
ls()
history() # press q key to quit history or help screens
help(ls)
?ls # same result

# vectors
c(1, 2, 3, 4, 5) # a simple vector
test1 <- c(1, 2, 3, 4, 5)
class(test1) # add 'vector' to whiteboard (second column)
test1
test2 <- c(3, 4, 5, 6, 7)
test3 <- 4
test1 + test2 # element-wise sum
test1 + test3 # 4 is used as a scalar
c(test1, test2, test3)
test2[1]
test2[4]
str(test2)
length(test2)
3:6
seq(0.3, 0.9, 0.05)
rep(c(4, 7), 8)
rep(seq(0, 1, 0.5), 2)
new.variable <- numeric()
new.variable
data.entry(new.variable)
new.variable
rm(new.variable)

# factors
gender <- c(rep("male", 20), rep("female", 30))
class(gender)
gender
gender <- factor(gender)
class(gender)
gender
summary(gender)
str(gender)
char <- as.character(gender)
fac <- as.factor(char)

# lists
mylist <- list(test1, test2, test3) # a simple list
class(mylist) # add 'list' to whiteboard (second column)
str(mylist)
mylist[[2]] # use double square brackets to access elements
mylist[[2]][4] # fourth element of the second list item


########## 2D DATA TYPES ##########

# matrices
test1
matrix(test1)
matrix(c(test1, test2), ncol = 2)
matrix(c(test1, test2), nrow = 2)
matrix(c(test1, test3), nrow = 2) # test3 is a scalar
mat <- matrix(c(test1, test2), ncol = 2) # save it
mat
mat[3, ] # show third row
mat[, 2] # show second column
mat[3, 2] # show second element in the third row
mat[, ] # show all
class(mat) # add 'matrix' to the whiteboard (second column)
str(mat)
colnames(mat)
colnames(mat) <- c("column A", "column B")
colnames(mat)
rownames(mat) <- c("row A", "row B", "row C", "row D", "row E")
mat
mat[, 2]
str(mat)
sum(mat)
dim(mat)
cat(paste("Number of rows:", dim(mat)[1]))
rowSums(mat)
colSums(mat)
cbind(mat, mat)
rbind(mat, mat)
t(mat) # transpose
mat
mat + 10 # scalar addition
mat * 10 # scalar multiplication
mat + mat # matrix addition
mat * mat # Hadamard product
mat %*% t(mat) # matrix multiplication

# data frames
mat
dat <- as.data.frame(mat)
dat
dat == mat # values are all the same, but data type is not
class(dat) # add 'data frame' to whiteboard (second column)
str(dat)
dat$"column B"
dat$newcol <- c("a", "b", "c", "d", "e")
dat
dat$newcol
str(dat)
newrow <- data.frame(10, 20, "f")
colnames(newrow) <- colnames(dat) # then use the same column names...
dat2 <- rbind(dat, newrow) # and finally collate them
str(dat2) # now the original data types were preserved!
dat2
