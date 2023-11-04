# TOCFL and CCCC wordlists

Parsed and cleaned up vocabulary wordlists for TOCFL and CCCC tests in .csv format.

*TOCFL (Test of Chinese as a Foreign Language)* is standardized Mandarin language proficiency test for non-native speakers, a taiwanese equivalent of mainland's HSK.

*CCCC (Children's Chinese Competency Certification)* is a related test aimed at non-native children speakers aged 7-12.

Files:
  * `tocfl.csv`: 202307 version (same as 202204), 7517 entries.
    * Source: https://tocfl.edu.tw/assets/files/vocabulary/8000zhuyin_202307.zip
  * `tocfl-2018.csv`: 2018 wordlist version, 7945 entries.
    * Source: https://clc.utaipei.edu.tw/p/405-1077-78054,c6557.php?Lang=en
  * `tocfl-pleco.txt`: a version of expanded list for import to Pleco as a user dictionary.
  * `tocfl.ipynb`: parser notebook.
  * `cccc.csv`: CCCC wordlist in .csv format, 1197 entries.
    * Source: https://tocfl.edu.tw/assets/files/vocabulary/CCCC_Vocabulary_2022.xls
    * 3 levels and has english definitions for all terms.
  * `tocfl-expanded.csv`, `tocfl-expanded-2018.csv`, `cccc-expanded.csv`: wordlists with term variants expanded, each variant on a separate line.
  * `data/`: additional data files used to generate .csv files:
    * `variants.csv`: manual disambiguations for ambiguous variant entries from TOCFL/CCCC lists.
    * `errata-pinyin.csv`: manual corrections to pinyin in TOCFL lists.

Columns:
  * `ID`: term's level + index (row number in original excel file which has one sheet per level)
    * TOCFL: `L0-1` = Novice 1, `L0-2` = Novice 2, `L1`..`L5` = Level 1..5 = CEFR A1/A2/B1/B2/C1+)
    * CCCC: `L0` = pre-A1, `L1` = A1, `L2` = A2 ([reference](https://tocfl.edu.tw/assets/files/literature/CCCC_LR_2022.pdf))
  * `Traditional`: term in traditional characters per TOCFL.
  * `Simplified`: converted to simplified characters.
  * `Pinyin`: pinyin with diacritics, slightly cleaned up from TOCFL sheets.
  * `POS`: part of speech, `/`-separated. See [description](https://tocfl.edu.tw/assets/files/vocabulary/8000_description_202204.pdf) on TOCFL website for the meaning of abbreviations.
  * `Meaning`: english definition (only CCCC list provides it).
  * `Variants`: for entries where TOCFL gives multiple variants of a term, an expanded disambiguated list in `term [pinyin] / term [pinyin] (POS) / ...` format.

Links:
  * [TOCFL website](https://tocfl.edu.tw/)
  * [TOCFL downloads page](https://tocfl.edu.tw/index.php/exam/download)
