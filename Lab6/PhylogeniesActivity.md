## Part I Questions

1. It was difficult to divide the collection into different species, especially from a 2D image of fossilized specimens. If they were cut in half it would be easier to distinguish them based on number of chambers. I figured size would be a poor indicator of different species because it would be impossible to distinguish a younger member of a larger species from an adult of a smaller one with size alone. Instead I first grouped all specimens into evolute or involute shells. From there I grouped them into varieties with ribbed shells and varieties with smooth shells, for a total of 4 different species. 

2. I found the most useful quantitative data to be the ratio of shell diameter to umbilical length as well as shell diameter to shell width. These two datasets are more useful than something like diameter because they are less likely to change as the organism ages. For qualitative data, I used  

3. It seems there are some specimens that are of the same species that are at different points in their ontogenic development. For example, specimen 4 and specimen 25 both have a U/D ratio of 0.34 and a W/D ratios of 0.23 and 0.21 respectively. Yet their total diameters are 39.5 mm and 59.5 mm respectively, which is quite the difference in size. 

4. As for sexual dimorphism, I had a very difficult time accounting for morphological variations in regards to sex. IF I knew the sexes of the specimens it would be easier to analyze, but it is difficult to determine if differences in traits are due to dsome kind of dimorphism or if it's a matter of them being different species. 



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

![ImageofPCAPlot](https://github.com/Connorzilla/WWUAdvancedPaleo/blob/master/Lab6/PCAHummingbird.png)

4. The hummingbird PCA seems to have little morphological groupings. There are no tight clusters that would indicate multiple specimens belong to one species. Perhaps morphological data isn't a good indicator of speciation here, or perhaps they are all of the same species.

## Part III Questions

1. Species D and E both belong to the clade with the synapomorphy 'Fangs longer than 6 inches'. 

2. Species D and E have a plesiomorphic sulfurous odor trait they share with species C. 

3. The clade containing species A and B have a synapomorphic trait of adorable eyelashes. 

4. Species C, D, and E have a sulfurous odor. 

5. Species D is distinguished from species E by its lack of a laser death ray. 

6. Adorable eyelashes are a synapomorphy for species A and B, wheras a fluffy tail is an autapomorphy for species A alone.

7. Family 1 is monophyletic, family 2 is polyphyletic, family 3 is paraphyletic. 

8. Species A should not be grouped into a family with species D and E. This would be a polphyletic group, as they have multiple common ancestors connecting them.

9. Group 1 is paraphyletic, group 2 is monophyletic, group 3 is paraphyletic, group 4 is monophyletic, and group 5 is polyphyletic.
