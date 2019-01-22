## PROBLEM SET 1
1. #### What class of object is mtcars? What function did you use to find out? 
I found that "mtcars" is a "data.frame", using: 

> class(mtcars)
[1] "data.frame"


2. #### Is islands defined as a 1-dimensional array or a vector? How did you find out? 
The "islands" is a vector, not a 1-dimensional array. I know this because vectors will return a dimensional test as null. Much like what happened:

> dim(islands)
NULL

3. #### How would you convert the data.frame beaver1 into a matrix?
You can use the class converting function:

>as(beaver1,"matrix") 

4. #### What is the name of the 8th landmass in the islands dataset? How did you find out?
Borneo. I found out by referencing the 8th sequence in the dataset using: 

Borneo 
   280 

5. #### What function would you use if you wanted to combine all three datasets into a single object?

Megalist<-list(mtcars,islands,beaver1)

6. #### Does islands consist of numeric data? How did you find out?

Yes, I used the function:
> is(islands,"numeric")
[1] TRUE

7. #### Code four different ways to subscript the 2nd row and 7th column of mtcars using bracket notation. (Hint: You are looking to return the number 17.02)

> mtcars["Mazda RX4 Wag","qsec"]
[1] 17.02
> mtcars["Mazda RX4 Wag",7]
[1] 17.02
> mtcars[2,"qsec"]
[1] 17.02
> mtcars[2,7]
[1] 17.02

8. #### How would you change the landmass values of "Iceland", "Kyushu", and "Tierra del Fuego" to 82, 21, and 10 in the islands dataset? (Hint: You will need to use subscripts and the <- operator).

To change the values of the respective landmasses, use the following simple functions:
> islands["Iceland"]<-82
> islands["Kyushu"]<-21
> islands["Tierra del Fuego"]<-10

9. #### Are there any times when the beaver in the beaver1 dataset had a temperature lower than 36.30 degrees? How did you find out?

No. I used the function:
beaver1["temp"]<36.30

The code returned all false values.

10. #### Take the sum of all elements in the column temp in the beaver1 dataset and call this value ValueA. Take the sume of all elements in the row Valiant in the mtcars dataset and call this value ValueB. Take the sum of the first 7 elements of the islands dataset and call this value ValueC. Divide ValueC by ValueB and add ValueA. What is your final answer? Show your code.

> sum(beaver1["temp"])
[1] 4202.29
> ValueA<-sum(beaver1["temp"])

I used ">mtcars" to determine what row the Valiant data was stored in then I used:
> sum(mtcars[6,])
[1] 385.54
> valueB<-sum(mtcars[6,])

> sum(islands[1:7])
[1] 37185
> ValueC<-sum(islands[1:7])

Finally the math:
> (ValueC/valueB)+ValueA
[1] 4298.739


