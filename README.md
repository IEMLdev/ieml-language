# ieml-language

## Overview

This is the repository for the IEML (information economy metalanguage) language database. 

In this repository, you will find : 
 - __dictionary/structure__ : the structure of IEML basic semantics units, the morphemes. This file is a space-separated csv file that contains the paradigms of the dictionary. The paradigms express each morpheme in a set of basic opposition with others morphemes (good/bad, start/ongoing/end, tall/small etc...) and by this process, defined theirs meanings.
 - __dictionary/descriptors__ : contains the translations and comments of the morphemes and their paradigms. This file is also a space separated csv.
 - __lexicons/{domain}/structure__ : the paradigms that structure a specific domain lexicon. As IEML is a universal language, the same IEML word can be defined in multiple domains (no silo). These files are also space separated csv.
 - __lexicons/descriptors__ : the translations and comments of traits, characters and words. The presence of a translation in this file for any such IEML lexical items defined this item in the database. This file is also a space separated csv.
 
The descriptors are for the moment only available in French and English. 

The IEML database aims to provide a memory of past interpretations to ground the language. Asymptotically, this database could be also used to automate the translation of IEML words toward natural languages, to decentralise the IEML interpretation process.

This database is a memory of the linguistic evolution of the IEML language  : the state of the repository is a synchronic view on the language and the commit view is a diachronic history.

##Versions
 - 0.1 : add dictionary and lexicon folder, add README and version file, add docs folder with database visualisation
 - 0.2 : refractor the database structure, remove yaml usage and use csv instead, separate the descriptors from the structure
 - 0.3 : refractor the database structure, separate the lexicons into domains but keep an unique descriptors file for the lexicons
