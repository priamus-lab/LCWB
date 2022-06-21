# Level Crossing Warning Bell (LCWB) Dataset


## Acknowledgement
These data are a product of a research activity conducted in the context of the [RAILS (Roadmaps for A.I. integration in the raiL Sector)](https://rails-project.eu) project which has received funding from the Shift2Rail Joint Undertaking under the European Union’s Horizon 2020 research and innovation programme under grant agreement n. 881782 Rails. The JU receives support from the European Union’s Horizon 2020 research and innovation program and the Shift2Rail JU members other than the Union.

## Disclaimers
The information and views set out in this document are those of the author(s) and do not necessarily reflect the official opinion of Shift2Rail Joint Undertaking. The JU does not guarantee the accuracy of the data included in this document. Neither the JU nor any person acting on the JU’s behalf may be held responsible for the use which may be made of the information contained therein.

This "dataset" has been created for scientific purposes only - and WITHOUT ANY COMMERCIAL purposes - to study the potentials of Deep Learning and Transfer Learning approaches. We are NOT re-distributing any video or audio; our files just contain pointers and indications needed to reproduce our study. The authors DO NOT ASSUME any responsibility for the use that other researchers or users will make of these data. 

## General Info
The .csv files contained in this folder (and subfolders) compose the Level Crossing (LC) Warning Bell (WB) Dataset.

When using any of these data, please mention:

De Donato, L., Marrone, S., Vittorini, V., Flammini, F., Narone, R., Mazzariello, C., Bernaudine, F., and Sansone, C., "Intelligent Detection of Warning Bells at Level Crossings through Deep Transfer Learning for Smarter Railway Maintenance", Submitted to Computers in Industry, Elsevier, 2022


## Content of the folder
This folder contains the following files and subfolders.

A subfolder named "LCWB Dataset" containing all the .csv composing the original LCWB Dataset:
- WB_data.csv (WB_labels.csv): representing data of the "Warning Bell (WB)" class;
- NA_data.csv (NA_labels.csv): representing data of the "No Alarm (NA)" class;
- GE_data.csv (GE_labels.csv): representing data of the "GEneric alarm (GE)" class.

A subfolder named "Additional Files" containing some .csv files related to data we adopted to further test the generalisation performances of the deep learning network leveraged in the aforementioned manuscript:
- FR_DE_data.csv (FR_DE_labels.csv), which have been used to test the generalisation performances of the network we exploited on LC WBs related to countries that were not considered in the training phase.
- LowHighIntesity_data.csv (LowHighIntesity_labels.csv), which have been used to study the correlation between the intesity of the audio and the network classification error.
    
A file "OtherEUCountriesWBs.txt" reporting the mapping between WB audio (labelled as "oc_warningbell" in the WB_data.csv file) and the related EU Country.


## Files Structure
Each XX_labels.csv file contains, for each entry, the following information:
- The identifier ("index") of the sub-class (which is not relevant in our case);
- The code-name ("mid") of the class, which is used in the XX_data.csv file to indicate the sub-class of a specific audio;
- The extend name of the class ("display_name").

Worth mentioning, sub-classes have not a specific purpose in our task. They have been kept to maintain as much as possible the structure of the "class_labels_indices.csv" file provided by [AudioSet](https://research.google.com/audioset/). The same applies to the XX_data.csv files, which have roughly the same structures of ["Evaluation", "Balanced train", and "Unbalanced train" Audioset .csv files](https://research.google.com/audioset/download.html).

Indeed, each XX_data.csv file contains, for each entry, the following information:
- ID: the identifier of the entry;
- YTID: the YouTube identifier of the video;
- start_seconds and end_seconds: which delimit the portion of audio (extracted from YTID) which is of interest for this task;
- positive_labels: the label(s) associated with the audio.


## Credits
The structure of the .csv files contained in this folder (and subfolders), as well as part of their content, was inspired by the .csv files composing the AudioSet dataset which is made available by Google Inc. under a [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license, while its ontology is available under a [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/) license.

Particularly, from AudioSet, we retrieved:
- The structure of the .csv files as discussed above.
- Data contained in GE_data.csv (which is a minimal portion of data made available by AudioSet) as well as the related 19 classes (in GE_labels.csv) which we selected among the about 527 classes included in the [AudioSet ontology](https://research.google.com/audioset/ontology/index.html).

Data contained in XX_data.csv files other than GE_data.csv have been retrieved by manually analysing several YouTube videos. Then, the related XX_labels.csv files have been created consequently.

More about downloading the AudioSet dataset can be found [here](https://research.google.com/audioset/download.html).


## Future Release
In the near future, a replication package is expected to be released by making available the source code of the Deep Learning Network adopted within the aforementioned manuscript.

