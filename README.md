# Summary

The treebank was subsequently augmented with a late Early Modern Irish syllabic poem consisting of 42 quatrains, described in a [separate section below](https://github.com/UniversalDependencies/UD_Irish-Cadhan#bardic-segment).

# Introduction

Irish underwent a major spelling standardization in the 1940’s and 1950’s,
and as a result it can be challenging to apply modern language technologies
to older, “pre-standard” texts.
For many years now, the general strategy for tagging and parsing
older Irish texts has been to pre-process them with an automatic
standardizer (Scannell, 2014), and to then use existing tools designed for 
the modern language. This approach has been successful, but has some
inherent limitations. First and foremost, since there are no resources
for directly tagging or parsing pre-standard texts, the standardizer must
do its job without the benefit of linguistic annotations.
This places an upper bound on the performance of the standardizer,
and therefore on the full pipeline for analyzing older texts.
In addition, there are certain grammatical phenomena that have all
but disappeared in the modern language (e.g. the dative case);
these cannot be properly handled with the existing approach.

Our primary aim in creating this treebank was to establish a test set for
evaluating lemmatization, tagging, and parsing of pre-standard Irish texts.
This should enable experimentation with various approaches
that we hope will eventually outperform the existing pipeline.
Although the test set is quite small (150 sentences, 3804 tokens), 
we hope to expand it enough to allow the training of a
parser designed to act directly on pre-standard texts. 

The corpus contains 25 sentences each from six different books
published between 1602 and 1936.
Texts published in the late 19th century and early 20th century
are much easier to process than older texts.  The orthography,
while quite different from the standard, is much more consistent
than what one finds in texts published before the 1880s. 
We selected three books
published in this later period, one
from each of the major Irish dialects: _Deoraidheacht_ by
Pádraic Ó Conaire (1910, Connacht Irish),
_Peig_ by Peig Sayers (1936, Munster Irish),
and _Scairt an Dúthchais_, a translation
of Jack London’s Call of the Wild by Niall Ó Domhnaill (1932, Ulster Irish).
We then selected three older (and consequently more challenging) texts
to round out the corpus: _Foras Feasa ar Éirinn_
by Seathrún Céitinn (1634), the 1602 translation of the
Gospel of John by Uilliam Ó Domhnaill,
and _Cín Lae Amhlaoibh_, a diary kept by Amhlaoibh Ó
Súilleabháin between 1827 and 1835.

The annotations were produced by standardizing the texts,
parsing them with a UDPipe model trained on the 
[modern Irish treebank](https://github.com/UniversalDependencies/UD_Irish-IDT),
projecting the annotations back to the source texts, and then
manually correcting the results. Full details are available
in Scannell (2022).

# Bardic segment

The Cadhan treebank includes a late Early Modern Irish syllabic (bardic) poem entitled <em>Mo mhallacht ort, a shaoghail</em> (“My curse on you, world”, c. 1655), consisting of 1004 tokens. The text was converted to a UD treebank by Dr Theodorus Fransen as part of a [CLS INFRA](https://clsinfra.io/) TNA fellowship at ÚFAL, Charles University, Prague (CZ), between September and December 2022. The version of the poem contained in the treebank is based on a lightly edited transcription available at https://bardic.celt.dias.ie/displayPoem.php?firstLineID=1387 (with the transcription error _'sar_ (correct: _'sas_) in 36c silently corrected). Each of the 42 quatrains corresponds to one sentence (with the prefixed identifier `bardic_1387`); it was found that splitting up these textual units resulted in too fragmented sentences. A recent edition and translation of the poem (Mac Cárthaigh, 2013) proved indispensable for proper morphological and syntactic analysis. For information about invaluable preparatory work on indexing and transcribing a large part of the extant Bardic corpus, as well as recent (non-UD) tagging and lemmatization efforts, see https://www.tcd.ie/Irish/research/bardic.php.

## Tokenization and annotation choices

Tokenization and annotation decisions are based on Scannell (2022, pp. 9–10). First of all, it is common for two words are written together, the first being a clitic (e.g. _'sgan_ for _is_ (_agus_) _gan_ in `bardic_1387-10`, `bardic_1387-14`, and `bardic_1387-27`); such cases are treated as multiword tokens. Lemmata are generally modern dictionary headwords based on [Ó Dónaill (1977)](https://www.teanglann.ie/en/fgb/). For pre-standard variants in our treebank for which a separate dictionary entry exists in Ó Dónaill (1977), the cross-referenced, standard headword has been used. This leads to a gender “mismatch” with certain tokens; for instance, gen.pl _ccóigidh_ “of the fifths” (i.e. provinces) (`bardic_1387-26`) has been mapped to the standard masculine lemma _cúige_ in our treebank, despite the existence of a modern feminine variant _cúigidh_. Two tokens do not have a corresponding modern lemma; _ima_ in _ima seach_ “in turn” (`bardic_1387-9`) is obsolete and has been lemmatized as _faoi_ according to modern usage, while _denas_ “(for a) while” (`bardic_1387-34`), which has no modern equivalent, is accompanied by the lemma _denus_, based on [dil.ie/15475](https://dil.ie/15475) (originally neuter but tagged as a masculine noun in our treebank).

While the language is for the most part Classical Modern Irish (c. 1200–1650), post-classical developments can clearly be seen, notably the simplification of the case system and conflation of case forms and constructions governed by prepositions (Mac Cárthaigh, 2013, pp. 47–48). For example, as Mac Cárthaigh (2013) points out, the accusative is used instead of the dative in _san saoghal_ “in this life” (`bardic_1387-39`; expected _san tshaoghal_), and acc./dat.sg _airdrígh_ “high-king” is used in subject position in `bardic_1387-3` (with the expected nom.sg _rí_ appearing in `bardic_1387-2`). Due to this “confusion”, and since the anchor point for tagging and parsing is standard Modern Irish, it was decided not to use the accusative feature, which is not part of the modern language and is therefore not used in the Modern Irish treebank. The dative case has only been assigned in cases where the noun has a distinctive dative form and occurs in actual dative position.

Some of the annotation decisions made are undoubtedly somewhat arbitrary. Echoing observations made in Scannell (2022, p. 9), some of the current annotation conventions might need to be re-evaluated in consultation with other Irish treebank maintainers, especially if older Early Modern Irish texts are added to the current treebank. It might also be worth pointing out that the language code `ga` (Modern Irish) has been employed for the entire corpus, including the “bardic” poem and the other 17th c. texts. The treebank maintainers are aware of the fact that a case could be made for assigning the (arguably somewhat fuzzy) language code `ghc` (https://iso639-3.sil.org/code/ghc), for <em>Hiberno-Scottish Gaelic</em>, to texts with the sentence ids `eoin`, `forasfeasa`, and `bardic_1387`. We leave this point for future discussion/work, but welcome feedback in the meantime.

# Acknowledgments

* Thanks to Teresa Lynn for her many years of work on the Irish treebank,
without which none of this research would be possible.
* Thanks to my undergraduate students Sai Shreyas Bhavanasi and Jianjun Zhang at Saint Louis University for many discussions that helped me understand the mathematics behind cross-lingual word embeddings more deeply.
* This project arose out of conversations with Charlie Dillon at the
Royal Irish Academy in early 2020 just before the COVID pandemic;
my thanks to Charlie and the RIA for hosting me during that visit,
and for inspiring this line of research.
* Dr Theodorus Fransen would like to acknowledge the CLS INFRA scheme (EU Horizon 2020 grant agreement No 101004984) and the invaluable help and advice received from his mentor Dr [Silvie Cinková](https://ufal.mff.cuni.cz/silvie-cinkova) during his fellowship at ÚFAL, Charles University, Prague. He is grateful to his collaborator Prof. Kevin Scannell for generating a first version of the “bardic” treebank using his projecting parser (Scannell, 2022) in addition to providing both technical and linguistic assistance. Dr Elaine Uí Dhonnchadha and Dr Eoin Mac Cárthaigh, both of Trinity College Dublin and the bardic@tcd project (https://www.tcd.ie/Irish/research/bardic.php), generously shared manually checked corpus files annotated with PAROLE tags, while Dr Mac Cárthaigh additionally elucidated various philological and linguistic matters related to the “bardic” poem _Mo mhallacht ort, a shaoghail_.

## References

* Mac Cárthaigh, Eoin (2013) [_Mo mhallacht ort, a shaoghail (c. 1655): dán is a sheachadadh_](https://www.jstor.org/stable/42910163), Ériu 63, pages 41–77.
* Scannell, Kevin P. (2014) [_Statistical models for text normalization and machine translation_](https://aclanthology.org/W14-4605/), Proceedings of the First Celtic Language Technology Workshop, pages 33–40, Dublin, Ireland. Association for Computational Linguistics and Dublin City University.
* Scannell, Kevin P. (2022) [_Diachronic Parsing of Pre-Standard Irish_](https://aclanthology.org/2022.cltw-1.2/), Proceedings of the 4th Celtic Language Technology Workshop within LREC2022, pages 7–13, Marseille, France. European Language Resources Association.


# Changelog

* 2022-11-15 v2.11
  * Initial release in Universal Dependencies.


<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.11
License: CC BY-SA 4.0
Includes text: yes
Genre: fiction nonfiction bible
Lemmas: manual native
UPOS: manual native
XPOS: not available
Features: manual native
Relations: manual native
Contributors: Scannell, Kevin
Contributing: here
Contact: kscanne@gmail.com
===============================================================================
</pre>
