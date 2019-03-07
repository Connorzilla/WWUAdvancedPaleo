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

The first line of code takes the Lucina data set we made earlier and calls out its "paleolng" column. The function "na.omit" removes any allows us to work with the data in a new object ("PaleoLng") without recieving errors from N/A data. 

The second line of code creates a sample with the sample function, drawing from the existing PaleoLng data set we created. The sample will set the length of vectors to that of the number of entries in the data set "PaleoLng". The replace=TRUE aspect of the code will allow the sample dataset to be overwritten with the PaleoLng values. Finally this new sample will be averaged with the mean function. 

7. Plot a kernel density graph of ResampledMeans. Show your code. Does the distribution look approximately Gaussian? Explain why you think it does or does not.

 >plot.tskernel(ResampledMeans)
 The plot looks fairly Gaussian because the values are most dense at a value a little above 24 Ma, and they are symettrically distributed with decreasing frequency as you move away from that value. 

8. Find the mean of ResampledMeans, is it similar to the mean of the original data?

> mean(ResampledMeans)
[1] 24.27991

Yes, the mean is certainly in the ballpark of what we would expect given earlier values of 23 or 24.

9. Sort ResampledMeans from lowest to highest. [Hint: We learned how to sort a vector in Lab 6].

> SortedMeans<-sort(ResampledMeans, decreasing=FALSE,)

10. Now that you have sorted ResampledMeans, what is the 2.5th percentile of ResampledMeans and what is the 97.5th percentile of Resampled means. If you do not know what a percentile is, or how to calculate it, you can use google. Show your code.

Finding which count in the sorted means data set corresponded to the 2.5 and 97.5 percentiles was fairly easy because there were one thousand unique numbers we generated. So we know 1000 times 0.025 is 25 and 1000 times 0.975 is 975. From there I could simply call those numbers out using the following code to find the percentiles:
> SortedMeans[25]
[1] 21.63986
> SortedMeans[975]
[1] 26.69052

11. Incidentally, these numbers (your answer to question 5) are the lower and upper confidence interval of the mean! Qualitatively explain why this is the case.

This is because we decided on a 95% confidence interval, so that percentage of the data, centered on the mean, is waht we care about. The other 2.5% on either side we consider anamolous and discard. 

## Problem Set 3

12. Based on the confidence intervals given above, do you think it likely or unlikely that Lucina is still alive?

I think it is unlikely. This is because the 2.5 percentile is 0 Ma, and that means that there's only 2.5% confidence that this taxa remains alive. I also googled it and didn't see any information, which doesn't bode well. 

13. Find the extinction confidence interval for the genus Dallarca. Show your code.

> estimateExtinction(Dallarca[,"min_ma"],0.95)
Earliest   Latest 
 2.58800 -3.88749 

14. A pure reading of the fossil record says that Dallarca went extinct at the end of the Pliocene Epoch. Based on its confidence interval, do you think it is possible that Dallarca is still extant (alive)?

No, I think that Dallarca is an extinct taxa and our coding or statistics methodology should be improved given the strange negative (future) extinction output. 

15. In this case, should we trust the confidence interval or a pure reading of the fossil record? Explain your reasoning.

We should obviously trust the fossil record over our confidence interval in this scenario. That's not to say we couldn't fine tune our statistic practices to remedy this discrepency though. 

## Problem Set 4

16. State one ecological reason why this assumption is unlikey to be true.

Organisms will be more sucessful for certain timespans and less successful in others given their adaptations to the environment. Their niche in time is not random, it is very dependent on the environment. Therefore, there will be periods when a taxa is succesful and will deposit many more fossils, and these periods are not random. 

17. State one geological reason why this assumpiton is unlikely to be true.

Preservation isn't constant throughout time either. Some periods will see increased sedimentation and burial than othersgiven a variety of conditions like climate, tectonics, and volcanism. 

## Problem Set 5

18. How many occurrences are in DataPBDB. How many are in ExtantData? How many occurrences were lost by limiting our anaysis to only extant bivalves?

There are 71,325 occurances of total bivalves in the PBDB, and only 932 extant ones. This means that 70,392 occurances were lost by looking only at the extant bivalves. 

19. How many unique( ) genera were in DataPBDB and ExtantData, respectively. Using this information, what percentage of Cenozoic bivalves in the PBDB are still extant today.



20. Find the stratigraphic range of fossil occurrences for each genus in the ExtantData dataset. If you do not remember how to do this, revisit Problem Set 1 of this lab.

21. Using your answer to question 3, find which genera in ExtantData are not extant according to the PBDB - i.e., do not have a minimum min_age of zero. Show your code.

22. Calculate the confidence interval for the extinction of the following genera (careful with your spelling!): Scrobicularia, Meiocardia, Dimya, Digitaria, Cuspidaria, Arctica, Aloides, Kurtiella, Gouldia, and Acrosterigma. Show your code. What percentage of these taxa have confidence intervals indicating that the taxon might still be extant?
