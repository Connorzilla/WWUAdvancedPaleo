## MYSTICAL RITE OF PASSAGE
1. #### Write a function that returns the phrase "Hello, world."

> Globalise<-function(Argument) {
    print(Argument)
    }
    
> Globalise("Hello world.")
[1] "Hello world." 

## PROBLEM SET
2. #### Load the iris dataset. Write a function that takes iris as its argument and returns three subsets of the data.frame, split by the three different types of species (saved as a single object).

Divide<-function(iris)
{
  
  Setosa<-iris[which(iris[,"Species"]=="setosa"),]
  Virginica<-iris[which(iris[,"Species"]=="virginica"),]
  Versicolor<-iris[which(iris[,"Species"]=="versicolor"),]
  
  return(list(Setosa, Virginica, Versicolor))
}

3. #### Write a function that takes iris as its argument. The function should, for each row, add Sepal.Length and Petal.Length if Sepal.Width is >3.1. It should subtract Petal.Length from Sepal.Length if Sepal.Width is <3.1. The answer should be returned as a vector.

Sepal<-function(iris[dim=1])
{
  if ([,"Sepal.Width"]>3.1){Vector1<-("Sepal.Length"+"Petal.Length")}
  else ([,"Sepal.Width"]<3.1){Vector2<-("Sepal.Length"-"Petal.Length")}
}

4. #### Load the mtcars dataset. Write a function that takes the number of cylinders as its argument. Have the function return the average miles per gallon (column mpg) for all cars with that number of cylinders (column cyl).

MPG<-function(mtcars)
{
sum{([,"cyl"]==6)}/(nrow(mtcars))}
}

5. #### Write a function that simulates 1,000,000 PowerBall drawings. A PowerBall drawing takes a randome sample of five numbers (without replacement) from 1-69, plus one powerball number ranging from 1-26. The function should return a single object recording all of your draws.



6. #### Write a function that takes a single set of lottery numbers (as a vector) as its argument. As before, write a function that simulates 1,000,000 PowerBall drawings. Have the function return a TRUE or FALSE value indicating if you won any of the drawings.

###Sorry I couldn't finish the assignment on time. To be honest I think this will take me hours to complete correctly on my own. I have no gift for coding...
