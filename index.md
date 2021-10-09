---
layout: entry
title: index.html
---

# IAHLT UD Guideline Recommendations
These guidelines are meant to supplement and ultimately be merged with the general UD Hebrew guidelines. Annotation decisions are based on general principles and compatibility with similar languages (esp. Arabic), though all other things being equal, backwards compatibility with UD_Hebrew-HTB is prioritized (for example in keeping together lexicalized complex adverbials, such as היום/ADV).

1. [Constructional changes from UD HTB](Constructional%20changes%20from%20UD%20HTB.html)
2. [General principles](https://github.com/IAHLT/heb-ud-gudielines/blob/gh-pages/General%20principles.html)
3. [Segmentation](Segmentation.html) 
4. [POS tagging in detail](Pos%20tagging%20in%20detail.html)
5. [Morphological features](Morphological%20features.html)
6. [Dependency relations in detail](Dependnecy%20relations%20in%20detail.html)
7. [Appendix](Appendix.html)

# Example Annodoc

~~~ ann
Barack Obama is the current president.
T1 PERSON 0 12 Barack Obama
~~~

~~~ sdparse
Dogs run
nsubj(run, Dogs)
~~~

Example provided in order:

~~~ conllx
1 Dogs dog _ NNS _ 2 nsubj
2 run run _ VBP _ 0 ROOT
~~~


~~~ conllx
2    רצים    רץ    _    VBP    _    0    ROOT
1    ילדים   ילד    _    NNS    _    2    nsubj
~~~
