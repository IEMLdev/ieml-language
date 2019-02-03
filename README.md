# ieml-language

## Overview

This is the repository for the IEML (information economy metalanguage) language database. 

This repository is composed of two folders :
 - __dictionary__ : contains all the files that defines the basic semantic units, the morphemes, of the IEML language. 
 - __lexicons__ : contains subfolder that contains the files that defines IEML words, build with morphemes from the dictionary.
 - __docs__ : database visualisation website. generated with the script [generate_site](https://github.com/IEMLdev/ieml-dictionary/blob/master/server/generate_site.py). accessible [here]().

## The dictionary definition

All the dictionary files in the `dictionary` folder are written in yaml and must conform to a syntax.
The syntax is described in this [file](https://github.com/IEMLdev/ieml-dictionary/blob/master/definition/dictionary_paradigm_schema.yaml) and is expressed in the 
[kwalify](http://www.kuwata-lab.com/kwalify/) schema syntax.

Each file from the `dictionary` folder defines a root paradigm.
A dictionary file is composed of multiple entries types :
 - __RootParadigm__ : the main opposition system, it implicitly defines a set of morphemes.
 - __Semes__ : the morphemes of this RootParadigm.
 - __Paradigms__ : additional semantic opposition systems between these morphemes.

Each of these entries are composed of the following fields:
 - __ieml__ : the IEML script of this entry
 - __translations__ : french and english translations
 - __comments__: a french and an english comment (optional)

A RootParadigm entry can also have the following field:
 - __inhibitions__ : a set of relations to ignore when computing the relations for this paradigm and its morphemes.

## The lexicons definition
The `lexicons` folder is composed of subfolder, that each contains yaml files in the [lexicon syntax](https://github.com/IEMLdev/ieml-dictionary/blob/master/definition/lexicons_schema.yaml).

Each yaml lexicon file defines a word paradigm and some of its words it contains.
A lexicon file is composed of one entry type :
 - __Words__ : the list of word defined in this file.

Each of word is composed of the following fields:
 - __ieml__ : the IEML usl of this entry (str)
 - __translations__ : french and english translations
 - __comments__: a french and an english comment (optional)


From these information, the script [generate_site](https://github.com/IEMLdev/ieml-dictionary/blob/master/server/generate_site.py) is able to compute the semantics relationships between the objects and display it [here]().

##Versions
 - 0.1 : add dictionary and lexicon folder, add README and version file, add docs folder with database visualisation
