Problem Set 1

> 20/20

1)

The North America is currently to the West of tHis position in the Cretaceous

2)

Meaning of col = A specification for the default plotting color
Meaning of lty = The line type
Meaning of add = add modern map on the cretaceous map
rgb() function creates colors corresponding to the given intensities of the red, green and blue primaries.
1 means max red, first 0 means no green, second 0 means no blue, 0.33 means 0.33 partially transparent.

3. 

`> AlbianMap<-downloadPaleogeography(Age=110)`

4. 

````R
> plot(CretaceousMap,col=rgb(0,0,1,0.33),lty=0)
> plot(ModernMap,col=rgb(1,0,0,0.33),lty=0,add=TRUE)
> plot(AlbianMap,col=rgb(0,1,0,0.33),lty=0,add=TRUE)
````

5.

There has been more movement north and south in the Eastern Hemisphere since the Albian.

6.

There has been more movement east and west in the Western hemisphere since the Albian.

Problem set 2:

1)

````R
> Boundary<-downloadPaleogeography(Age=56)
> plot(Boundary,col=rgb(1,0,0,0.33),lty=0)
````

2.

````R
> DataPBDB<-downloadPBDB(Taxa=c("Anthozoa"),StartInterval="Paleocene",StopInterval="Eocene")
````

3.

````R
> nrow(DataPBDB)
[1] 2847
````

4.

````R
> dimnames(DataPBDB)

occurrence_no: A number that uniquely identifies the occurrence
collection_no: The identifier of the collection with which the occurrence is associated
difference: If the identified name is different from the accepted name, this field gives the reason why
early_interval: The specific geologic time range associated with this occurrence.
reference_no: The identifier of the reference from which this data was entered
geoplate: The identifier of the geological plate
family: Select only occurrences which are identified to a family, genus, or species
record_type: the type of the object
identified_name: The taxonomic name by which this occurrence was identified
accepted_name: The value of this field will be the accepted taxonomic name corresponding to the identified name.
late_interval: the interval that ends the specific geologic time range associated with this occurrence, if different from the value of early_interval
paleomodel: The primary model specified by the parameter. This field will only be included if more than one model is indicated.
phylum: the name of the phylum in which this occurrence is classified
genus: The name of the genus in which this occurrence is classified. 
reid_no: If this occurrence was re-identified, a unique identifier for the re-identification
identified_rank: The taxonomic rank of the identified name, if this can be determined
accepted_rank: The taxonomic rank of the accepted name.
max_ma: the early bound of the geologic time range associated with this occurrence
paleolng: The paleolongitude of the collection, evaluated according to the primary model indicated by the parameter
class: The name of the class in which this occurrence is classified
flags: A record representing an identification that has been superseded by a more recent identification will have the letter R in this field, however mostly empty
identified_no: The unique identifier of the identified taxonomic name
accepted_no: The unique identifier of the accepted taxonomic name in this database
min_ma: The late bound of the geologic time range associated with this occurrence (in Ma)
paleolat: the paleolatitude of the collection, evaluated according to the primary model indicated by the parameter
order: the name of the order in which this occurrence is classified
````

5.

````R
> points(DataPBDB[c("paleolng","paleolat")])
````

6.
The most of the Anthozoa occurrences in the Eastern Hemisphere are in Europe. Anthozoa are primarily marine organisms. The ocean must have existed in this region of the world during this time.

> Epicontinetnal sea, yes.

The Problem Set 3:
1.
````R
> DataPBDB<-downloadPBDB(Taxa=c("Perissodactyla"),StartInterval="Paleogene",StopInterval="Paleogene")
```` 
 
2.
Defining attribute: nonruminant ungulates
Examples: horses, tapirs, and rhinoceros

3.
````R
> DataPBDB[which(DataPBDB[,"collection_no"]==112723),]
````

4.
501 tectonic plate is associated with this collection
The modern day region of he world that this geoplate id corresponds to is Pakistan.

5.

````R
> nrow(DataPBDB[which(DataPBDB[,"geoplate"]==501),])
[1] 84
````

6.
Region X has moved towards south and slightly west from Albian to the present day.

7.
The first scenario is implausible, because the first occurrence of Perissodactyla in Asia was found in China when it was the age of Thanetian. There were on occurrences of Perissodactyla in region X at the time.

The second scenario is more plausible, because after Thanetian, more occurrences were found both in region X and China. As a result, we can infer that species migrated from China to region X.

The third scenario can be plausible as well, because China was not the only place on Eurasia that had occurrences of Perissodactyla. They were also found in Europe. As a result, the occurrences of Perssodactyla found in region X later might originate from Europe. Furthermore, it is kind of hard to say if the species of Perissodactyla in China and region X both came from a third region, Europe. This is because occurrences found in China and Europe were from roughly the same period of time. So, it is hard to tell if the occurrence firstly originated in China or Europe. 
