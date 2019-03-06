## Problem Set 1

There are four columns in DataPBDB relevant to the age of an organism: early_interval, late_interval, max_ma, and min_ma. Because we rarely have a precise date, we generally give the age of an occurrence as a range. This range can be expressed by interval names or by numbers.

1. What do the max_ma and min_ma columns of DataPBDB represent? If you do not intuitively know, you can always check the Paleobiology Database API documentation.

These two columns represent the early bound and the late bound (respectively) of a taxa in the fossil record.

2. What is oldest age of each genus? [Hint: Use the tapply( ) and max( ) functions we've used in previous labs]. Show the code you would use to find out.

The oldest age of each genus can be found with the code:
>tapply(DataPBDB[,"genus"], DataPBDB[,"max_ma"],max)

3. What is the youngest age of each genus? [Hint: Use the tapply( ) and min( ) functions we've used in previous labs]. Show the code you would use to find out.

The same code is used except "max_ma" is substituted with "min_ma":
> tapply(DataPBDB[,"genus"], DataPBDB[,"min_ma"],max)

4. Find which genus has the most occurrences in the dataset [Hint: Use the table( ) function!]. What code did you use?

Genus Anadara has 2105 occurances:
>max(table(DataPBDB[,"genus"]))
[1] 2105

5. What is the stratigraphic range of this taxon (i.e., your answer to question 4). Show your code.

I used the following code which spat out a table of stratigraphic ranges ranging from 0 to 56 Ma...

> Anadara<-DataPBDB[which(DataPBDB[,"genus"]=="Anadara"),]
> tapply(Anadara[,"genus"],Anadara[,"min_ma"],max)


## Problem Set 2

6. Qualitatively describe what is happening in the following lines of code. A good answer should identify what the different arguments are for each function, and what they are used for.
> PaleoLng <- na.omit(Lucina$paleolng)
> mean(sample(PaleoLng, length(PaleoLng), replace=TRUE))

7. Plot a kernel density graph of ResampledMeans. Show your code. Does the distribution look approximately Gaussian? Explain why you think it does or does not.

8. Find the mean of ResampledMeans, is it similar to the mean of the original data?

9. Sort ResampledMeans from lowest to highest. [Hint: We learned how to sort a vector in Lab 6].

10. Now that you have sorted ResampledMeans, what is the 2.5th percentile of ResampledMeans and what is the 97.5th percentile of Resampled means. If you do not know what a percentile is, or how to calculate it, you can use google. Show your code.

11. Incidentally, these numbers (your answer to question 5) are the lower and upper confidence interval of the mean! Qualitatively explain why this is the case.

## Problem Set 3

12. Based on the confidence intervals given above, do you think it likely or unlikely that Lucina is still alive?

13. Find the extinction confidence interval for the genus Dallarca. Show your code.

14. A pure reading of the fossil record says that Dallarca went extinct at the end of the Pliocene Epoch. Based on its confidence interval, do you think it is possible that Dallarca is still extant (alive)?

15. In this case, should we trust the confidence interval or a pure reading of the fossil record? Explain your reasoning.

## Problem Set 4

16. State one ecological reason why this assumption is unlikey to be true.

17. State one geological reason why this assumpiton is unlikely to be true.

## Problem Set 5

18. How many occurrences are in DataPBDB. How many are in ExtantData? How many occurrences were lost by limiting our anaysis to only extant bivalves?

19. How many unique( ) genera were in DataPBDB and ExtantData, respectively. Using this information, what percentage of Cenozoic bivalves in the PBDB are still extant today.

20. Find the stratigraphic range of fossil occurrences for each genus in the ExtantData dataset. If you do not remember how to do this, revisit Problem Set 1 of this lab.

21. Using your answer to question 3, find which genera in ExtantData are not extant according to the PBDB - i.e., do not have a minimum min_age of zero. Show your code.

22. Calculate the confidence interval for the extinction of the following genera (careful with your spelling!): Scrobicularia, Meiocardia, Dimya, Digitaria, Cuspidaria, Arctica, Aloides, Kurtiella, Gouldia, and Acrosterigma. Show your code. What percentage of these taxa have confidence intervals indicating that the taxon might still be extant?
