## Problem Set

1. Download a dataset from the Paleobiology Database that includes all Ordovician-age animals (i.e., Animalia). Name the object Ordovician. What code did you use?

> Ordovician <-velociraptr::downloadPBDB(Taxa="Animalia", StartInterval = "Ordovician", StopInterval = "Ordovician")

2. Clean up the poorly resolved genus names. What function and/or code did you use?

> Ordovician<-velociraptr::cleanTaxonomy(DataPBDB, "genus")

3. Turn you object Ordovician into a community matrix of the samples by genera, where the samples are different geoplate codes. Geoplate codes denote different paleocontinents, so by doing this, your community matrix will list which genera were present on which paleocontinents during the Ordovician. Cull this matrix so that each sample has a minimum of 25 taxa and each taxon occurs in at least two samples. Show your code.

> PresenceOrdo <- velociraptr::presenceMatrix(Ordovician,Rows="geoplate",Columns="genus")
> PresenceOrdo <- velociraptr::cullMatrix(PresenceOrdo,Rarity=2,Richness=25)

4. Preform a DCA on your new community matrix. Analyze your DCA with a plot. Do you think that the orientation of samples along either axis 1 or axis 2 is related to the average latitude or longitude of each plate in question? Explain how you determined your answer, and shwo your code. Hint: information about the paleolatitude and paleolongitude of different geoplates is included in the data you originally downloaded (i.e., the object Ordovician)

I used the code:
> OrdoDCA<-vegan::decorana(PresenceOrdo, ira=0)
> plot(OrdoDCA,display="sites")

The result looks something like this: 


![ImageDCA](https://github.com/Connorzilla/WWUAdvancedPaleo/blob/master/Lab8/DCA%20of%20Ordovician.png)


Considering that life tends to prefer the equator, I would say that DCA 2 is latitude as samples are more clustered in the middle of that axis. DCA 1 would then be the longitude, as samples are more spread out along the Ordovician Earth on this axis. 
