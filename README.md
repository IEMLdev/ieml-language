# ieml-language

## Overview

This is the repository for the IEML (information economy metalanguage) language database. 

In this repository, you will find structures files, that defines the semantic relationship between the basic elements of the language - the morphemes, and syntagmatic relationship between the morphemes to form words :
 - __structure/dictionary__ : the structure of IEML basic semantics units, the morphemes. It express each morpheme in a set of basic opposition with others morphemes (good/bad, start/ongoing/end, tall/small etc...). Each opposition system is called a paradigm, and the positions that the morphemes have into theirs paradigms defines theirs meaning. The structure made by all the paradigms is called the IEML dictionary. This file is a space-separated csv file with the following columns : ['root', 'paradigms', 'inhibitions']. (root = the main paradigms, paradigms = sub-paradigm in the root, inhibitions = semantics relations to ignore)
 - __structure/lexicons/{domain}__ : These are the paradigms that structure a specific domain lexicon. The lexicons paradigms are build from the morphemes defined in the __structure/dictionary__ file. These files defines paradigms that have been made using [intlekt](https://intlekt.io/?morpheme=). These files are also space separated csv with the following columns : ['paradigm', 'domain'].

The descriptors files are contained into the __descriptors__ folder, these files contains the translations and definition of the ieml items in natural languages. In the folder, there is a file per syntatic level:
 - morpheme : contains the translations and comments of morphemes and theirs paradigms. This file contains the translations for all the dictionary and definition for the main paradigms.
 - trait : contains the translations and comments of traits and theirs paradigms. The trait are sequence of morpheme and trait paradigms are list of sequence of morphemes.
 - character : contains the translations and comments of characters and theirs paradigms. The character is a hierarchy of trait, the character is a hierarchy of trait where at least one of the trait is a paradigm.
 - words : contains the list of 

All descriptor files are space separated csv and have the same columns interface ['ieml', 'language', 'descriptor', 'values'] :
 - ieml : the ieml string of the object
 - language : 2 letter language code, for the moment, only 'fr' and 'en' exists.
 - descriptor : a value taken from ['translations', 'comments']
 - values : a list of string, if descriptor == 'comments' the string can be in the Markdown format.


The IEML database aims to provide a memory of past interpretations to statistically ground the language. Asymptotically, this database could be also used to automate the translation of IEML traits, characters and words toward natural languages. 

## Versions
 - 0.1 : add dictionary and lexicon folder, add README and version file, add docs folder with database visualisation
 - 0.2 : refractor the database structure, remove yaml usage and use csv instead, separate the descriptors from the structure
 - 0.3 : refractor the database structure, separate the lexicons into domains but keep an unique descriptors file for the lexicons
