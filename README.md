# TOCFL wordlists

This repository contains parsed and cleaned up vocabulary wordlists for TOCFL and related tests in .csv format. Current as well as some historical versions.

***TOCFL*** *(Test of Chinese as a Foreign Language)*: standardized Mandarin language proficiency test for non-native speakers, a taiwanese equivalent of Mainland's HSK.

***CCCC*** *(Children's Chinese Competency Certification)*: related test aimed at non-native children speakers aged 7-12.

***TBCL*** *(Taiwan Benchmarks for the Chinese Language)*: reference wordlist and grammar points list for constructing language tests, but not a test per se.

## Wordlists

`tocfl-202307.csv`: current 2022/2023 TOCFL wordlist
  * 7517 terms (7849 with variants, 7480 unique)
  * 7 levels (in ID column together with term index):
    * `L0-1nnn` = Novice 1 (準備級一級), pre-A1
    * `L0-2nnn` = Novice 2 (準備級二級), pre-A1
    * `L1-nnnn` = Beginner (入門級), CEFR A1
    * `L2-nnnn` = Basic (基礎級), CEFR A2
    * `L3-nnnn` = Intermediate (進階級), CEFR B1
    * `L4-nnnn` = Advanced (高階級), CEFR B2
    * `L5-nnnn` = Fluent (流利級), CEFR C1-C2
  * Contains part-of-speech tags for all terms, but no definitions
  * Source: [8000zhuyin_202307.zip](https://tocfl.edu.tw/assets/files/vocabulary/8000zhuyin_202307.zip) / [8000zhuyin_202204.zip](https://tocfl.edu.tw/assets/files/vocabulary/8000zhuyin_202204.zip)

`tocfl-20180419.csv`: 2018 TOCFL wordlist version
  * 7945 terms (8106 with variants, 7399 unique), 7 levels
  * Source: https://web.archive.org/web/20200227052851/http://www.sc-top.org.tw/download/8000zhuyin.zip

`tocfl-20160215.csv` ... `tocfl-20170324.csv`: older versions of TOCFL wordlist.

`top-20100915.csv`, `top-20111208.csv`: 2010/2011 wordlist versions, TOCFL test back then was called SC-TOP
  * 4-5 levels (2010 file has a single level for CEFR A1-A2, L2 here)
  * Terse English definitions for all terms -- useful for looking up the main intended sense or deciphering some more obscure entries on newer lists e.g.
    * `只,zhǐ,M,"Individual measure word for box, watch or ring."`
    * `不等,bùděng,Post,vary in number` - postposition, were changed to N in bulk on newer lists.
  * Different part-of-speech tags, following PAVC textbooks.
  * Source: [800+800020100915.xls](https://web.archive.org/web/20160116074948/http://www.sc-top.org.tw/download/800+800020100915.xls), [list20111208.xls](https://web.archive.org/web/20140908011551/http://www.sc-top.org.tw/download/L1-L5vocabualry%20list20111208.xls)

`cccc.csv`: CCCC 2022 wordlist
  * 1197 terms (1344 with variants, 1312 unique)
  * 3 levels ([reference](https://tocfl.edu.tw/assets/files/literature/CCCC_LR_2022.pdf)):
    * `L1-nnn` = 萌芽級, pre-A1
    * `L2-nnn` = 成長級, CEFR A1
    * `L3-nnn` = 茁壯級, CEFR A2
  * Part-of-speech and basic English definitions for all terms.
  * Source: https://tocfl.edu.tw/assets/files/vocabulary/CCCC_Vocabulary_2022.xls

`tbcl.csv`: TBCL wordlist
  * 14425 terms (14868 with variants, 14731 unique)
  * 7 levels
  * Definitions, part-of-speech and examples for ~1500 beginner level (L1-L3) words.
  * Source: https://coct.naer.edu.tw/download/tech_report/

## Other files

  * `tocfl.ipynb`, `tbcl.ipynb`: parser scripts
  * `tbcl-affix.csv`: TBCL affix table (suffixes and prefixes)
  * `tbcl-chars.csv`: TBCL character table by level (slightly different from characters used in the wordlist)
  * `tbcl-grammar.csv`: TBCL grammar points table
  * `tocfl-cedict.csv`, `tbcl-cedict.csv`: wordlists merged with CC-CEDICT definitions
  * `errata.csv`: corrections applied to pinyin in original lists to fix various errors
  * `expanded/*.csv`: wordlists with term variants expanded, each variant on a separate line
  * `pleco/*.txt`: wordlists for import to Pleco as flashcards or a user dictionary -- useful to get level tags for terms in Pleco

## Format

Columns in .csv files:
  * `ID`: term's level + index (row number in source excel file)
  * `Traditional`: term in traditional characters
    * May contain `()/,` to indicate variants.
    * See Variants field or expanded/*.csv files to get clean a hanzi.
  * `Simplified`: term converted to simplified characters
  * `Pinyin`: pinyin with diacritics, cleaned up and normalized. Tone changes are not indicated.
  * `POS`: part of speech, /-separated.
    * See [description](https://tocfl.edu.tw/assets/files/vocabulary/8000_description_202204.pdf) on TOCFL website for details.
    * Follows part of speech in dangdai textbooks / TengPOS
    * TOP wordlists follow older PAVC textbooks
  * `Meaning` (CCCC/TOP/TBCL wordlists): English definition
  * `WFreq`, `SFreq` (TBCL): writing and speech frequency (in Sinica corpus?)
  * `MOE` (TBCL): reference IDs for looking up terms on https://dict.concised.moe.edu.tw/dictView.jsp?ID=
  * `Variants`: for entries where TOCFL gives multiple variants of a term, an expanded disambiguated list as a JSON list of objects with alternatives column values.

## Links

  * https://tocfl.edu.tw/
  * https://coct.naer.edu.tw/TBCL/
  * [https://web.archive.org/web/\*/http://www.sc-top.org.tw/download/\*](https://web.archive.org/web/*/http://www.sc-top.org.tw/download/*)
