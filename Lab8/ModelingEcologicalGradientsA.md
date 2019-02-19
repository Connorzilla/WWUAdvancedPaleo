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
