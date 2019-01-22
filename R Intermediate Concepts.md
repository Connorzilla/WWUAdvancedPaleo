##SECTION 1 QUESTIONS
1. #### What does the replace = argument of the sample( ) function do?

The replace = argument gives the items in the list a hidden numeric value. 

2. #### Using as(MyMatrix,"numeric") will not convert MyMatrix to a numeric data! Can you use another property of logicals other than as( ) that will convert the logicals of MyMatrix to 0's and 1's?

Yes, using the function: 
MyMatrix[which(MyMatrix==TRUE)]<-1

3. #### If you wanted to check if all the elements in each row are true, how would you do this?

Use the 'which' and 'apply' functions on dimension 1 (rows) and find which one sums to all 'TRUE' values with the function:
> which(apply(MyMatrix,1,sum)==TRUE)
integer(0)

##SECTION 2 QUESTIONS
4. #### How many times does the number 7 occur in MyMatrix?

Nine times according to the function:
> MyMatrix[which(MyMatrix==7)]
[1] 7 7 7 7 7 7 7 7 7
> length(MyMatrix[which(MyMatrix==7)])
[1] 9

5. #### How do you find the sum of each column?

Use the sum and apply function in tandem:
> apply(MyMatrix,2,sum)
 [1] 46 35 32 50 45 61 38 47 38 39 57 50

6. #### How do you find the product of each column?

Do the same thing using product instead of sum:
> apply(MyMatrix,2,prod)
 [1]  100000    9600    6804  840000  241920 7741440   12600  403200
 [9]   70000   38880 4408992 1008000

7. #### How can you change every instance of the number 1 to 11?

Replacing every number 1 to 11 in the matrix is actually fairly straightforward:
> MyMatrix[which(MyMatrix==1)]<-11

8. #### How many values in MyMatrix are greater than 3 and less than 8?

I found 34 values using the function:

> MyLogical<-(MyMatrix > 3 & MyMatrix < 8)
> length(MyMatrix[which(MyLogical)])
[1] 34

9. #### How can you change the elements of column 12 into character data, while keeping columns 1-11 as numeric data?

First I made column 12 into its own entity and converted that to character data:
C12<-MyMatrix[,12]
C12c<-as.character(C12)
> typeof(C12c)
[1] "character"

Then I made the first 11 columns of MyMatrix into a smaller matrix with only 11 columns:
> MySmallerMatrix<-MyMatrix[,1:11]
> MySmallerMatrix

Finally I combined the character array and the smaller matrix into one data frame:
> MyGoodFrame<-data.frame(MySmallerMatrix,C12c)

10. #### Find which rows of MyMatrix have a sum >70. Make a new version of MyMatrix where the 13th column is a set of TRUE and FALSE values denoting which rows have a sum >70. (Hint: What type of object allows you to store both logical and numeric data at once?)

First I wrote code to determine which rows had a sum of over 70:
> MyLogical<-apply(MyMatrix,1,sum)
> MyLogical
[1] 69 66 70 60 61 70 75 67

Then I wrote a logical statement that made anything 70 or under FALSE and named it 'Col13:
> MyLogical>70
[1] FALSE FALSE FALSE FALSE FALSE FALSE  TRUE FALSE
> Col13<-(MyLogical>70)

Finally I made a data frame combining this object and MyMatrix:
> MyFrameGame<-data.frame(MyMatrix,Col13)

