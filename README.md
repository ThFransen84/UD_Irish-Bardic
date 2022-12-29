# Summary

This is the Cadhan Aonair UD treebank, initially consisting of 
150 sentences randomly sampled from six pre-standard Irish texts. The treebank was subsequently augmented with a late Classical Irish (bardic) poem, described in a [separate section below](https://github.com/UniversalDependencies/UD_Irish-Cadhan#bardic-segment).

# Bardic segment
The Cadhan treebank includes a late Classical Irish (bardic) poem entitled <em>Mo mhallacht ort, a shaoghail</em> (“My curse on you, world”, c. 1655), consisting of 43 sentences (stanzas). The text was converted to a UD treebank by Dr Theodorus Fransen as part of a [CLS INFRA](https://clsinfra.io/) TNA fellowship at ÚFAL, Charles University, Prague (CZ), between September and December 2022. The version of the poem contained in the treebank is based on a lightly edited transcription available at https://bardic.celt.dias.ie/displayPoem.php?firstLineID=1387. A recent edition and translation of the poem (Mac Cárthaigh 2013) proved indispensable for proper morphological and syntactic analysis. For information about invaluable preparatory work on indexing and transcribing a large part of the extant Bardic corpus, as well as recent (non-UD) tagging and lemmatisation methods, see https://www.tcd.ie/Irish/research/bardic.php.

## Tokenisation and annotation

Tokenisation and annotation decisions are based on Scannell (2022, pp. 9–10). It is worth pointing out that it is common in Bardic poetry — or in the transcribed manuscript texts at least — for two words to be written together, the first appearing as a clitic (e.g. _'sgan_ for _is_ (_agus_) _gan_); such cases are treated as multiword tokens. Lemmata are generally modern dictionary headwords based on [Ó Dónaill (1977)](https://www.teanglann.ie/en/fgb/). For pre-standard variants in our treebank for which a separate dictionary entry exists in Ó Dónaill (1977), the cross-referenced, standard headword has been used. This leads to a gender “mismatch” with _ccóigidh_ “(of the) fifths (i.e. provinces)” (`bardic_1387-26`), which has been mapped to the standard masculine lemma _cúige_ in our treebank, despite the existence of a modern feminine variant _cúigidh_. Two words do not have modern equivalents; _ima_ in _ima seach_ “in turn” (`bardic_1387-9`) has been mapped to the modern lemmatic equivalent _faoi_, while _denas_ “(for a) while” (`bardic_1387-34`) is accompanied by the lemma _denus_ as per [dil.ie/15475](dil.ie/15475) (but tagged in our treebank as a masculine rather than a neuter noun, the latter category of which has long disappeared from the language and is therefore not available as a modern lexical feature). 

While traces of the prescriptive usage of case forms are salient in our poem, we see a confusion between dative and accusative constructions typical of the post-Classical period (Mac Cárthaigh 2013, pp. 47–48), in addition to the conflation in Early Modern Irish of the accusative and nomative case. For this reason, the accusative case feature, which does not exist in the modern language, has not been used; the dative is only assigned in cases where the noun has a distinctive dative form (but not where an original dat.sg exists as a variant nom.sg in the modern language, as per Ó Dónaill (1977), e.g. _caroid_ (_caraid_) “friend” (`bardic_1387-17`) for standard _cara_). As Scannell (2022, p. 9) has pointed out, current treebank annotation conventions might need to be reevaluated based on discussions with other Irish treebank maintainers. 

# Acknowledgments

* Thanks to Teresa Lynn for her many years of work on the Irish treebank,
without which none of this research would be possible.
* Thanks to my undergraduate students Sai Shreyas Bhavanasi and Jianjun Zhang at Saint Louis University for many discussions that helped me understand the mathematics behind cross-lingual word embeddings more deeply.
* This project arose out of conversations with Charlie Dillon at the
Royal Irish Academy in early 2020 just before the COVID pandemic;
my thanks to Charlie and the RIA for hosting me during that visit,
and for inspiring this line of research.
* Dr Theodorus Fransen would like to acknowledge the CLS INFRA scheme (EU Horizon 2020 grant agreement No 101004984) and the invaluable assistance received from his mentor Dr [Silvie Cinková](https://ufal.mff.cuni.cz/silvie-cinkova) (ÚFAL, Charles University, Prague). He would also like to thank Dr Eoin Mac Cárthaigh and Dr Elaine Uí Dhonnchadha, both of Trinity College, Dublin, for helpful feedback and generously sharing manually checked corpus files annotated with PAROLE tags.

## References

* Mac Cárthaigh, Eoin (2013) [_Mo mhallacht ort, a shaoghail (c. 1655): dán is a sheachadadh_](https://www.jstor.org/stable/42910163), Ériu 63 (2013): 41–77.
* Scannell, Kevin P. (2014) [_Statistical models for text normalization and machine translation_](https://cs.slu.edu/~scannell/pub/coling14.pdf), Proceedings of the 1st Celtic Language Technology Workshop at COLING 2014, Baile Átha Cliath, 23 August 2014.
* Scannell, Kevin P. (2022) [_Diachronic Parsing of Pre-Standard Irish_](https://cs.slu.edu/~scannell/pub/dppsi.pdf), Proceedings of the 4th Celtic Language Technology Workshop (CLTW 2022) at LREC 2022, Marseille, France, 20 June 2022.

