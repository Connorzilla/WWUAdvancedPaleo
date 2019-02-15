## Excercise Questions Part 1

Let's use the folowing paper as an example (which you can find on Canvas):

Holland, S. M. and M. E. Patzkowsky. 2007. Gradient ecology of a biotic invasion: Biofacies of the type Cincinnatian series (Upper Ordovician), Cincinnati, Ohio Region, USA. Palaios, 22:392-407.

Use the reference tool to look up collections associated with this paper, then answer the following questions.

1. How many collections are associated with this reference?

This article has 704 associated collections on the PBDB.

2. What is the reference ID number for the article?

This article is referenced as 24429. 

Once you have answered the above questions, click the view collections hyperlink at the bottom of the page to see all the collections associated with this study. Click to view Collection No. 72438, then answer the following questions:

3. The first two taxa in the taxonomic list are bryozoans, and the third taxon listed is Rafinesquina alternata. Next to the taxonomic name is the citation (Conrad 1830). What is the class, family, genus and species of the fourth taxon in the taxonomic list?

Class: Strophomenata
Family: Strophomenidae
Genus: Strophomena
Species: planumbona

2. In what county was the data collected?

The United States (Union County, Indiana). 

3. What age (Period) is the data from?

The Ordovician. 

4. What is the name of the geologic formation that the data was collected from?

The Liberty fomation, composed of packstone and mudstone.

## Exercise Questions Part 2

Once you have familiarized yourself with the page, search for the genus Abra. Abra is a genus of bivalve.

1. Zoom in so that you can see from Texas to Florida and from Florida to New York. Some of the occurrences are orange and others are yellow. What is the significance of the different colors?

These colors represent the time period in which the fossils occured. Orange represents the Paleogene period. Yellow can either represnt the Neogene or the entiritey of the Cenozoic Era. 

2. Zoom back out. Add an additioanl filter to the search bar, the Ypresian stage. The Ypresian is a time interval ranging from 47.8-56.0 million years ago. In what countries are there Ypresian occurrences of Abra?

Most occurances of Ypresian members of Abra are in England, there is also an occurance in Belgium and an occurance near the Gulf of Mexico in the US.

3. Clear the Abra and Ypresian filters from the search. Look for the genus Ambonychia (another genus of bivalve). Within the United States, find the city with the most occurrences of Ambonychia. What is the name of this city?

Cincinati, Ohio (US).

4. What age (Period) are most Ambonychia occurrences?

Most occurrences are from the Ordovician. 

5. During this time period, were most occurrences of Ambonychia arrayed parallel or perpendicular to the equator?

Most of the occurences are arranged parallel to and along the equator. 

6. Click on the little insect icon on the left side of the screen. This brings up taxonomic information about the target taxon. What order does Ambonychia belong to?

Order: Myalinida.

## Exercise Questions Part 3

1. All occurrences of Ambonychia in the Lexington Limestone as a JSON

https://paleobiodb.org/data1.2/occs/list.json?datainfo&rowcount&base_name=Ambonychia

2. All occurrences of mammals present in the Paleocene through Oligocene epochs as a csv

https://paleobiodb.org/data1.2/occs/list.csv?datainfo&rowcount&base_name=mammalia&interval=Paleocene,Oligocene

3. All opinions on the order Testudines in the Mesozoic

https://paleobiodb.org/data1.2/occs/opinions.csv?datainfo&rowcount&base_name=Testudines&interval=Mesozoic&op_type=all

4. All collections of Aves, Marsupialia, and Sirenia in the United States as a csv

https://paleobiodb.org/data1.2/colls/list.csv?datainfo&rowcount&base_name=Aves,Marsupialia,Sirenia&cc=US

5. All occurrences of the gastropod genus Ficus as a csv

https://paleobiodb.org/data1.2/occs/list.csv?datainfo&rowcount&base_name=Ficidae 

6. What family does the genus Gastrocopta belong to?

Family: Gastrocoptidae.

7. There is only one occurrence of Isoetes in Portugal. What age is it?

This occurrence is from the Aptian stage of the Cretaceous period. 

8. What is the age of the oldest occurrence of Gastrocopta?

The oldest Gastrocopta occurence is from the Eocene. 

9. There is only one occurrence of Tiktaalik in the PBDB. Was that occurrence located in the tropics or the extratropics when that organism was alive?

Despite the near-arctic fossil discovery location, this occurrence would have been located in the tropics during the Devonian. 

10. There are two occurrences of Namacalathus in Siberia. What geologic formations are they found in?

These occurrences are found in the Raiga and Kotodzha formations.

## Exercise Questions Part 4

1. In your morphometrics lab, you downloaded a csv file of ammonite sizes from a GitHub URL directly into R. What code would you use to download the following PBDB data directly into R?

I simply coded:
> URL<-"https://paleobiodb.org/data1.2/colls/list.csv?base_name=Mammut&interval=Pliocene"
> MammutPil<-read.csv(URL, row.names=1)

2. Download the data from the URL above into R. What are its dimensions?

The data has two dimensions:
> dim(MammutPil)
[1] 70 13

3. Did the above call use the occurrences, collections, references, opinions, or specimens route?

This call used the collections, "colls", route. 

4. What genus is being called for? What is its colloquial name? What age was the call limited to?

This route calls for genus Mammut, a group of mammoths. The call is specifically for Pliocene mammoths. 

5. Look through the service doumentation for the appropriate route (based on your answer to Question 2). Find out how to extend the age search range from the Miocene Epoch through the Pleistocene Epoch. Give the new data query URL.

Instead of just setting the interval to Pliocene, you susbstitute that with a the intended time periods seperated with a dash:
>URL<-"https://paleobiodb.org/data1.2/colls/list.csv?base_name=Mammut&interval=Miocene-Pleistocene"

6. What URL would you use to show the paleocoordinates (i.e., paleolatitude and paleolongitude) of each data point?

To show the paleocoordinates we use the show parameter and set it equal to "paleoloc". 
URL<-"https://paleobiodb.org/data1.2/colls/list.csv?base_name=Mammut&interval=Pliocene&show=paleoloc"

## Exercise Questions Part 5

1. Write an R function that will take a taxonomic name (as a character string) and an interval (as a character string) as its argument, and will download all fossil occurrences in R. 

>downloadPBDB<-function(taxon,interval)
{
    {
        Link<-
        {paste("httpsL//paleobiodb.org/data1.2/occs/list.csv?taxon_name=",
               taxon,"&interval=",interval)}
    }
    {
        read.csv(Link,row.names=1)  
    }
    
}
