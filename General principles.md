

General principles

Lemma
Lemmas should be provided in their non-vocalized form (כתיב מלא).
In case that there is more than one commonly-used spelling for a word – For example, words that originate from other languages and can be written with or without the letter אל"ף (e.g. מטאפורה  vs מטפורה) – please provide the form that is more frequent (use Google search to determine in case you are not sure).
Removal of reconstructed articles and של/את   
We recommend completely disregarding reconstructed articles and possessives, which in UD_Hebrew-HTB lead to the insertion of a pseudo-token with the word form _של_ in possessives such as:
הזמנה_ + _של_+_הם → הזמנת+ם
And articles fused with prepositions as in:
 ב_+_ה_+_בית → ב+בית
This keeps the data closer to the analysis in Arabic treebanks and makes use of general purpose tools easier, as well as allowing any additional annotations to be aligned to the base text, while avoiding blatant tokenization errors which disrupt downstream usage.
To keep this modification trivial and bidirectionally reversible, we add a feature Definite=Def on prepositions preceding fused articles. The possessive is trivially reversible since it is the only way in which a PRON token is dominated as nmod:poss without the preposition של.
Prepositions with subsumed articles take both Definite=Def and PronType=Art. Additionally, clitic possessive pronouns take Definite=Def, but PronType=Prs (see Definite and PronType in Morphology).
Elliptical promotion
In keeping with current UD guidelines, functional elements are promoted to the function of their elided parent, such as promoting prepositions without an object to take the role of nmod/obl, as well as subtypes such as nmod:poss, as required. For example in the following של is not labeled as ‘case’:

![](https://lh6.googleusercontent.com/5lFL9gAF-92MWSH23J8nuxblkcSXjzG3sUsbqh0RF3kaMXjBo3xbzmir4723Ay4sEOtBEfT0q4Y8iEnveHz1DdlJucB5XF0li0lHRUrHyDymHYRVWdDjojPLH13KlemnR3M77PkI=250x250)


Promotion can generally lead to POS tags carrying unusual dependency relations, for example a VERB can be promoted to substitute a missing NOUN that would control it, resulting in VERBs taking relations such as obj. For example in the following analysis:

![](https://lh4.googleusercontent.com/yyz7wcW6CrPgYryNXvyUNk9cri8b9DU0y7AMJ9XmEGBq85kW1kiQn7-yu0InzS460t16yqo52pvWnyC-piHa0L2sX6KUHTWBPpwRDR4bHA6fFqoskg4ouWnpl2yH04bh7G5nZPdv=s0)


The missing word מה should be the object of לתאר (as in לתאר את מה שמתרחש). Because UD prioritizes preserving the argument structure of the matrix clause (and more generally, of whichever structure is ‘higher’ in the tree), the VERB מתרחש stands in for the obj function from the argument structure of לתאר, and will also be the promoted head dominating the case relation for את, but it will still be tagged VERB. For more discussion of this example, see Free relatives below.
