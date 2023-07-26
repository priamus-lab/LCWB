# Level Crossing Warning Bell (LCWB) Dataset


## Acknowledgement
These data are a product of a research activity conducted in the context of the [RAILS (Roadmaps for A.I. integration in the raiL Sector)](https://rails-project.eu) project which has received funding from the Shift2Rail Joint Undertaking under the European Union’s Horizon 2020 research and innovation programme under grant agreement n. 881782 Rails. The JU receives support from the European Union’s Horizon 2020 research and innovation program and the Shift2Rail JU members other than the Union.

## Disclaimers
The information and views set out in this document are those of the author(s) and do not necessarily reflect the official opinion of Shift2Rail Joint Undertaking. The JU does not guarantee the accuracy of the data included in this document. Neither the JU nor any person acting on the JU’s behalf may be held responsible for the use which may be made of the information contained therein.

This "dataset" has been created for scientific purposes only - and WITHOUT ANY COMMERCIAL purposes - to study the potentials of Deep Learning and Transfer Learning approaches. We are NOT re-distributing any video or audio; our files just contain pointers and indications needed to reproduce our study. The authors DO NOT ASSUME any responsibility for the use that other researchers or users will make of these data. 

## General Info
The CSV files contained in this folder (and subfolders) compose the Level Crossing (LC) Warning Bell (WB) Dataset.

When using any of these data, please mention:

De Donato, L., Marrone, S., Flammini, F., Sansone, C., Vittorini, V., Nardone, R., Mazzariello, C., and Bernaudin, F. (2023). Intelligent detection of warning bells at level crossings through deep transfer learning for smarter railway maintenance. Engineering Applications of Artificial Intelligence, 123, 106405. DOI: https://doi.org/10.1016/j.engappai.2023.106405

## Content of the folder
This folder contains the following subfolders and files.

A subfolder named "Data Files" containing all the CSV files related to the data composing the LCWB Dataset:
- WB_data.csv (WB_labels.csv): representing data of the "Warning Bell (WB)" class;
- NA_data.csv (NA_labels.csv): representing data of the "No Alarm (NA)" class;
- GE_data.csv (GE_labels.csv): representing data of the "GEneric alarm (GE)" class.

A subfolder named "LCWB Dataset" containing all the JSON files that show how the aformenteioned data have been distributed among training, validation, and test sets:
- IT_Distribution.json and UK_distribution.json respectively shows how Italian (IT) WBs and British (UK) WBs have been distributed;
- The same goes for NA_Distribution.json and GE_Distribution.json which show the distribution of NA and GE data respectively;
- DatasetDistribution.json simply incorporates the content of the aforementioned JSON files in a unique file that can be exploited to obtain exactly the same dataset we adopted in our analyses.

A subfolder named "Additional Files" containing some CSV files related to data we adopted to further test the deep neural network leveraged in the aforementioned manuscript:
- FR_DE_data.csv (FR_DE_labels.csv): representing data that have been used to test the generalisation performances of the network we exploited on LC WBs related to countries that were not considered in the training phase.
- Noises_data.csv (Noises_labels.csv): representing the noises that were considered to study the behaviour of the network in case of noisy data.


## CSV Files Structure
Each XX_labels.csv file contains, for each entry, the following information:
- The identifier ("index") of the sub-class (which is not relevant in our case);
- The code-name ("mid") of the class, which is used in the XX_data.csv file to indicate the sub-class of a specific audio;
- The extend name of the class ("display_name").

Worth mentioning, sub-classes have not a specific purpose in our task. They have been kept to maintain as much as possible the structure of the "class_labels_indices.csv" file provided by [AudioSet](https://research.google.com/audioset/). The same applies to the XX_data.csv files, which have roughly the same structures of ["Evaluation", "Balanced train", and "Unbalanced train" Audioset CSV files](https://research.google.com/audioset/download.html).

Indeed, each XX_data.csv file contains, for each entry, the following information:
- ID: the identifier of the entry;
- YTID: the YouTube identifier of the video;
- start_seconds and end_seconds: which delimit the portion of audio (extracted from YTID) which is of interest for this task;
- positive_labels: the label(s) associated with the audio.


## Credits
The structure of the CSV files contained in this folder (and subfolders), as well as part of their content, was inspired by the CSV files composing the AudioSet dataset which is made available by Google Inc. under a [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license, while its ontology is available under a [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/) license.

Particularly, from AudioSet, we retrieved:
- The structure of the CSV files as discussed above.
- Data contained in GE_data.csv (which is a minimal portion of data made available by AudioSet) as well as the related 19 classes (in GE_labels.csv) which we selected among the hundreds of classes included in the [AudioSet ontology](https://research.google.com/audioset/ontology/index.html).

Data contained in XX_data.csv files other than GE_data.csv have been retrieved by manually analysing several YouTube videos. Then, the related XX_labels.csv files have been created consequently.

More about downloading the AudioSet dataset can be found [here](https://research.google.com/audioset/download.html).
