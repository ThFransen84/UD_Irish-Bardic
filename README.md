# Summary

This repository contains a [Universal Dependencies](https://universaldependencies.org/) (UD) treebank of a late Early Modern Irish syllabic poem consisting of 42 quatrains. The treebank was integrated with the [Cadhan Aonair](https://github.com/UniversalDependencies/UD_Irish-Cadhan) corpus of pre-standard Irish texts, created and maintained by Prof. Kevin Scannell, as part of UD v2.12 (2023-05-15).

# Background

The Early Modern Irish syllabic (“bardic”) poem is entitled <em>Mo mhallacht ort, a shaoghail</em> (“My curse on you, world”, c. 1655) and consists of 1004 tokens. The text was converted to a UD treebank by Dr Theodorus Fransen as part of a [CLS INFRA](https://clsinfra.io/) TNA fellowship at ÚFAL, Charles University, Prague (CZ), between September and December 2022. The basis for this work was a (noisily annotated) CoNLL-U file produced by a projecting parser for pre-standard Irish texts (Scannell, 2022) applied to a transcription of the poem available at https://bardic.celt.dias.ie/displayPoem.php?firstLineID=1387*. It was decided to treat each quatrain as one sentence (with the prefixed identifier `bardic_1387-`), with sentence 43 constituting _closure_ (a repetition of (part of) the first line of the poem). It was found that splitting up the poem into smaller units resulted in too fragmented sentences. A recent edition and translation of the poem (Mac Cárthaigh, 2013) proved indispensable for proper morphological and syntactic analysis. For information about invaluable preparatory work on indexing and transcribing a large part of the extant Bardic corpus, as well as recent (non-UD) tagging and lemmatization efforts, see https://www.tcd.ie/Irish/research/bardic.php.

*with the transcription error _'sar_ (for _'sas_) in 36c being silently corrected (thanks to Dr Eoin Mac Cárthaigh for pointing this out).
# Tokenization and annotation choices

Tokenization and annotation decisions are based on Scannell (2022, pp. 9–10). First of all, it is common for two words to be written together, the first being a clitic (e.g. _'sgan_ for _is_ (_agus_) _gan_ in `bardic_1387-10`, `bardic_1387-14`, and `bardic_1387-27`); such cases are treated as multiword tokens. Lemmata are generally modern dictionary headwords based on [Ó Dónaill (1977)](https://www.teanglann.ie/en/fgb/). For pre-standard variants in our treebank for which a separate dictionary entry exists in Ó Dónaill (1977), the cross-referenced, standard headword has been used. This leads to a gender “mismatch” with certain tokens; for instance, gen.pl _ccóigidh_ “of the fifths” (i.e. provinces) (`bardic_1387-26`) has been mapped to the standard masculine lemma _cúige_ in our treebank, despite the existence of a modern feminine variant _cúigidh_. Two tokens do not have a corresponding modern lemma; _ima_ in _ima seach_ “in turn” (`bardic_1387-9`) is obsolete and has been lemmatized as _faoi_ according to modern usage, while _denas_ “(for a) while” (`bardic_1387-34`), which has no modern equivalent, is accompanied by the lemma _denus_, based on [dil.ie/15475](https://dil.ie/15475) (originally neuter but tagged as a masculine noun in our treebank).

While the language is for the most part Classical Modern Irish (c. 1200–1650), post-classical developments can clearly be seen, notably the simplification of the case system and conflation of case forms and constructions governed by prepositions (Mac Cárthaigh, 2013, pp. 47–48). For example, as Mac Cárthaigh (2013) points out, the accusative is used instead of the dative in _san saoghal_ “in this life” (`bardic_1387-39`; expected _san tshaoghal_), and acc./dat.sg _airdrígh_ “high-king” is used in subject position in `bardic_1387-3` (with the expected nom.sg _rí_ appearing in `bardic_1387-2`). Due to this “confusion”, and since the anchor point for tagging and parsing is standard Modern Irish, it was decided not to use the accusative feature, which is not part of the modern language and is therefore not used in the Modern Irish treebanks. The dative case has only been assigned in cases where the noun has a distinctive dative form and occurs in actual dative position.

Some of the annotation decisions made are undoubtedly somewhat arbitrary. Echoing observations made in Scannell (2022, p. 9), some of the current annotation conventions might need to be re-evaluated in consultation with other Irish treebank maintainers, especially if older Early Modern Irish texts are added to the current treebank. It might also be worth pointing out that the language code `ga` (Modern Irish) has been employed for the [Cadhan Aonair](https://github.com/UniversalDependencies/UD_Irish-Cadhan) corpus, including the “bardic” poem and the other 17th c. texts. A case could be made for assigning the (arguably somewhat fuzzy) language code `ghc` ([<em>Hiberno-Scottish Gaelic</em>](https://iso639-3.sil.org/code/ghc)) to texts with the sentence ids `eoin`, `forasfeasa`, and `bardic_1387`. We leave this point for future discussion/work. Any feedback on annotation and other matters is greatly welcomed.

# Acknowledgments

* Thanks to Dr Teresa Lynn for her many years of work on the Irish treebank,
without which none of this research would be possible.
* The treebank maintainer would like to acknowledge the CLS INFRA scheme (EU Horizon 2020 grant agreement No 101004984) and the invaluable help and advice received from his mentor Dr [Silvie Cinková](https://ufal.mff.cuni.cz/silvie-cinkova) during his fellowship at ÚFAL, Charles University, Prague. 
* He is also grateful to his collaborator Prof. Kevin Scannell for generating a first version of the “bardic” treebank using his projecting parser (Scannell, 2022) in addition to providing both technical and linguistic assistance. 
* Dr Elaine Uí Dhonnchadha and Dr Eoin Mac Cárthaigh, both of Trinity College Dublin and the bardic@tcd project (https://www.tcd.ie/Irish/research/bardic.php), generously shared manually checked corpus files annotated with PAROLE tags, while Dr Mac Cárthaigh additionally elucidated various philological and linguistic matters related to the “bardic” poem _Mo mhallacht ort, a shaoghail_.

## References

* Mac Cárthaigh, Eoin (2013) [_Mo mhallacht ort, a shaoghail (c. 1655): dán is a sheachadadh_](https://www.jstor.org/stable/42910163), Ériu 63, pages 41–77.
* Scannell, Kevin P. (2022) [_Diachronic Parsing of Pre-Standard Irish_](https://aclanthology.org/2022.cltw-1.2/), Proceedings of the 4th Celtic Language Technology Workshop within LREC2022, pages 7–13, Marseille, France. European Language Resources Association.
