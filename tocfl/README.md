# TOCFL and CCCC wordlists

Parsed and cleaned up vocabulary wordlists for TOCFL and CCCC tests in .csv format.

*TOCFL (Test of Chinese as a Foreign Language)* is standardized Mandarin language proficiency test for non-native speakers, a taiwanese equivalent of mainland's HSK.

*CCCC (Children's Chinese Competency Certification)* is a related test aimed at non-native children speakers aged 7-12.

Files:
  * `tocfl.csv`: current 2022/2023 TOCFL wordlist, 7517 entries.
    * Source: https://tocfl.edu.tw/assets/files/vocabulary/8000zhuyin_202307.zip
    * Source: https://tocfl.edu.tw/assets/files/vocabulary/8000zhuyin_202204.zip (identical vocabulary)
  * `tocfl-2018.csv`: 2018 wordlist version, 7945 entries.
    * Source: https://clc.utaipei.edu.tw/p/405-1077-78054,c6557.php?Lang=en
  * `tocfl.ipynb`: parser notebook.
  * `cccc.csv`: CCCC wordlist in .csv format, 1197 entries.
    * Source: https://tocfl.edu.tw/assets/files/vocabulary/CCCC_Vocabulary_2022.xls
    * 3 levels and has english definitions for all terms.
  * `tocfl-expanded.csv`, `tocfl-expanded-2018.csv`, `cccc-expanded.csv`: wordlists with term variants expanded, each variant on a separate line.
  * `pleco-*.txt`: versions of expanded lists for import to Pleco as flashcards or a user dictionary -- useful to get level tags for terms in Pleco.
  * `data/`: additional data files used as inputs when generating .csv files:
    * `variants.csv`: manual disambiguations for ambiguous variant entries from TOCFL/CCCC lists.
    * `errata-pinyin.csv`: manual corrections to pinyin in TOCFL/CCCC lists, mostly missing apostrophes, but also a few real errors.

Columns:
  * `ID`: term's level + index (row number in original excel file which has one sheet per level)
    * TOCFL: `L0-1nnn` = Novice 1 (準備級一級), `L0-2nnn` = Novice 2 (準備級二級), both pre-A1, `L1-nnnn`..`L5-nnnn` = Level 1..5 (入門級/基礎級/進階級/高階級/流利級) = CEFR A1/A2/B1/B2/C1+.
    * CCCC: `L1-nnn` = pre-A1 (萌芽級), `L2-nnn` = 成長級 / A1, `L3-nnn` = 茁壯級 A2 ([reference](https://tocfl.edu.tw/assets/files/literature/CCCC_LR_2022.pdf)).
  * `Traditional`: term in traditional characters per TOCFL. May contain `()/,` to indicate variants -- see `Variants` field or `*-expanded.csv` files to get clean a hanzi.
  * `Simplified`: term converted to simplified characters.
  * `Pinyin`: pinyin with diacritics, slightly cleaned up from TOCFL sheets. Tone changes are not indicated.
  * `POS`: part of speech, `/`-separated. See [description](https://tocfl.edu.tw/assets/files/vocabulary/8000_description_202204.pdf) on TOCFL website for details.
  * `Meaning`: english definition (only CCCC list provides it).
  * `Variants`: for entries where TOCFL gives multiple variants of a term, an expanded disambiguated list as a JSON list of objects with alternatives column values.

Links:
  * [TOCFL website](https://tocfl.edu.tw/)
  * [TOCFL downloads page](https://tocfl.edu.tw/index.php/exam/download)
