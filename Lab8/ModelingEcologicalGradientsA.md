## Problem Set 1

1. How many genera are in the Miocene, Early Jurassic, Late Cretaceous, and Pennsylvanian epochs (not total, but in each epoch)? What code did you use to find out?

I found 653 genera in the Miocene, 177 in the Early Jurassic, 396 in the Late Cretaceous, and 121 in the Pennsylvanian using the code:
>sum(PresencePBDB["Miocene",])
Substituting Miocene with other epochs as needed. 

2. How many geologic epochs are included in this dataset? What code did you use to find out?

There are 29 unique geologic epochs.
> dim(PresencePBDB)
[1]  29 942

3. Which epochs contain specimens of the genus Mytilus (a type of mussel)? What code did you use to find out?

16 of the 29 epochs of the data set contain Mytilus specimens.
> which(PresencePBDB[,"Mytilus"]==1)
         Pridoli   Early Devonian    Late Jurassic           Eocene 
               8               10               14               15 
 Late Cretaceous Early Cretaceous  Middle Jurassic        Paleocene 
              16               17               18               19 
       Oligocene          Miocene   Early Jurassic      Pleistocene 
              20               21               22               23 
 Middle Triassic    Late Triassic         Pliocene   Early Triassic 
              25               26               27               28 

4. Look at the epochs in the geologic timescale. Using your answer to question 3, in which epochs can we infer that Mytilus was present, even though we have no record of them in the PBDB? How did you deduce this?

According to the PBDB, this clade appeared as early as the Pridoli epoch all the way back in the Silurain and as recently as the Plestiocene epoch. Assuming this genera did not appear, go extinct, and magically reappear, one can safely say /Mytilus/ existed in all epochs in between.
This includes the Early, Late, and Middle Devonian; the Pennsylvanian and Mississipian; the Cisuralian, Guadalupian, and Lopingian. Clearly there is a wide chronological gap in their fossil record. 

## Problem Set 2

1. Using your own custom R code, find the Jaccard similarity of the Pleistocene and Miocene "samples" in your PresencePBDB matrix. It is possible to code this entirely using only functions discussed in the R Tutorial.

The number of shared genera:
> Numbershared<-which(((PresencePBDB["Pleistocene",]==1)&(PresencePBDB["Miocene",]==1))

The number of genera in the Pleistocene NOT in the Miocene:
> NumberPleistocene<-which((PresencePBDB["Pleistocene",]==1)&(PresencePBDB["Miocene",]==0))

The number of genera in the Miocene NOT in the Pleistocene:
> NumberMiocene<-which((PresencePBDB["Pleistocene",]==0)&(PresencePBDB["Miocene",]==1))

To find the Jaccard similarity:
> (sum(Numbershared))/((sum(Numbershared))+(sum(NumberPleistocene))+(sum(NumberMiocene)))
[1] 0.8492264

2. How can you convert your similarity index to a distance?



3. Install and load the vegan package. Read the help file for the vegdist( ) function, then use vegdist( ) to calculate the Jaccard distance of the Miocene and Pleistocene samples from the PresencePBDB matrix. Your answer should be identical to your answer to Question two.

4. Using the vegdist( ) function, calculate the Jaccard distances for all of the following epochs in PresencePBDB: Pleistocene, Pliocene, Miocene, Oligocene, Eocene, Paleocene. What code did you use? Which two epochs are the most dissimilar?
