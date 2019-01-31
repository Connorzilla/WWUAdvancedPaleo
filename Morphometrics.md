### Morphometric Plot of Osteostracans

![Image of Morphometrics]
(https://github.com/Connorzilla/WWUAdvancedPaleo/blob/master/Osteostracans%20Plot.png)

Unfortunately the plot won't embed, but if you look at my repository for it, you'll see that there's quite a spread in terms of feature placement for the osteostracans. The plot shows that the 'wing'-like features are the most varied between members, but there's also substantial diversity in terms of specimen length. 

### PCA Plot

The PCA plot and summaries describe how individual specimens vary from the mean of all osteostracans, like the morphometric plot but more useful when looking at individuals apart from the group. 

For example, according to the plot, individuals 29 and 8 are least alike in terms of principal component 1. This aspect of the morphology seems to be how long the specimen was from head to rear. Specimen 8 was very short wheras specimen 29 was long in build.

![Image of PCA Plot]
(https://github.com/Connorzilla/WWUAdvancedPaleo/blob/master/OsteostracansPCAPlot.png)

As for PC 2, this seems to be a measure of how wide an the individuals are, or their 'wingspan'. Specimen 3, /Belonaspis puella/ is very narrow in body plan while specimen 4, /Benneviaspis angelica/ has very wide outcroppings. 

![Image of Belonaspis]
(https://github.com/Connorzilla/WWUAdvancedPaleo/blob/master/Belonaspis_puella.png)
This is /Belonaspis puella/.

![Image of Benneviaspis]
(https://github.com/Connorzilla/WWUAdvancedPaleo/blob/master/Benneviaspis_anglica.png)
This is /Benneviaspis anglica/.

The majority of diversity of a group can be pinpointed to the first two or three principal components, as illustrated by this bar graph:

![Image of Bar Graph]
(https://github.com/Connorzilla/WWUAdvancedPaleo/blob/master/RplotofOSteostracans.png)

This is further shown when I try to plot the 18th PC against the 1st. There is very little difference on the PC 18 axis as most of the diversity of the organisms comes from PC 1. 

I did so using this code in R-studio:
>osteoPCA <- plotTangentSpace(osteoGPA$coords, axis1 = 1, axis2 = 18, label = TRUE)

![Image of PC1 vs PC18]
(https://github.com/Connorzilla/WWUAdvancedPaleo/blob/master/PC1andPC18Graph.png)

### Conclusion
Principal components analysis has a wide variety of modern and paleobiological applications. With it, you could quickly examine a whole population of specimens and see what makes each individual unique from the average. For example, you could use this to describe the diversity of sponges (just kidding they're asymettrical). Or you could use it to describe leaf patterns in a variety of plants in order to figure out how to identify one species from many others. 
