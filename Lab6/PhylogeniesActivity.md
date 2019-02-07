## Part I Questions

1. It was difficult to divide the collection into different species, especially from a 2D image of fossilized specimens. If they were cut in half it would be easier to distinguish them based on number of chambers. I figured size would be a poor indicator of different species because it would be impossible to distinguish a younger member of a larger species from an adult of a smaller one with size alone. Instead I first grouped all specimens into evolute or involute shells. From there I grouped them into varieties with ribbed shells and varieties with smooth shells, for a total of 4 different species. 

2. I found the most useful quantitative data to be the ratio of shell diameter to umbilical length as well as shell diameter to shell width. These two datasets are more useful than something like diameter because they are less likely to change as the organism ages. For qualitative data, I used  



## Part II Questions (Subsection 1)

1. The element names listed are "land", "links", "species", "site", and "outline"

2. According to the function below, the objects in plethodon are:
> class(plethodon[[1]])
[1] "array"
> class(plethodon[[2]])
[1] "matrix"
> class(plethodon[[3]])
[1] "factor"
> class(plethodon[[4]])
[1] "factor"
> class(plethodon[[5]])
[1] "matrix"
> class(plethodon[[6]])

3. The first object is a three dimensional array, you can tell with the function:
> dim(plethodon[[1]])
[1] 12  2 40

## Part II Questions (Subsection 2)

1. The object "land" represents the hummingbird landmark data. 

2. I performed a procrustes on the hummingbird data using the code:
> ProcrustesHummingbirds<-gpagen(hummingbirds$land)

3. The following is a PCA plot of the hummingbird data:


