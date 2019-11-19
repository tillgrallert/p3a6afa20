---
title: "Catch me if you can! Notes"
author: Till Grallert
date: 2019-08-10
tags:
    - periodical studies
    - social network analysis
    - stylometry
    - Arabic periodicals
    - digital humanities
---

# to do

- **done** make a map of the holding institutions
- check meaning of weight in stylo() output
    + kind of **done**
- process stylo() edges table, to include further columns
    + **done**
    + number of works in worldcat
- make TEI bibliography of the most referenced periodicals (minimum 2 journals in my corpus): currently 36 titles
    + **done**
    + **done**: write XSLT to enrich bibliography and link `<title>`s to bibliography
    + **done**: improve CSV of referenced periodicals
- comments on corpus
    + period needs to be mentioned
- terminology
    + *ṣāḥib*: owner, concessionary, publisher
    + *mudīr masʾūl*: responsible editor, director responsible, director-in-charge
        * there seems to be no clear equivalent outside the former Ottoman realms
        * it is still used in Arabic and Turkish
    + *raʾis al-taḥrīr*: editor-in-chief (wikipedia), Rédacteur en chef (wikipedia)
    + *mudīr al-taḥrīr*: managing editor
    + *muḥarrir*: editor

## missing bits

1. conclusion: **done**
2. introduction:
    -
2. one paragraph on the most prolific authors in *Lughat al-ʿArab*
3. citation networks!
    - Maxim Romanov:
        - gazetteer: **done**
        - prosopography
    - Will Hanley: **done**
    - Torsten Wollina
    - Kathryn Schwartz
    - Adam Mestyan: **done**
    - add references to works that critiqued shamela.ws
3. expand on the results of stylometric analysis: **done**
4. literature on *Lughat al-ʿArab*
    + there isn't much
        * Hilary Kilpatrick presented a paper on Anastās al-Karmalī at Firas' workshop in June 2019

## anonymous authorship

- the majority of articles were published anonymously
    + is this mentioned in the literature?
        * Ayalon 1995
            - "anonymous": used twice, not with regard to authorship
            - "unkown": six pages
            - "authorship": not mentioned
            - seems to favour "writer" over "author"
- is it really illegal?
    + I cannot, for the sake of it, find a reference for my claim
- the signing editor is responsible as if he was the author
- Publishers issued repeated calls on authors to come forward and provide their identities; e.g. {thamarat 181; lisan 442; lisan 1301; thamarat 573; thamarat 729}.


## editors as authors

- instead of claiming that the common assumption is that editors wrote all anonymous articles themselves, state that this is the obvious first idea.
    + check Czygan 2012 on this issue
        * makes the implicit assumption by stating that it isn't entirely clear if Ḍiyā Bey authored the final 36 issues all by himself (p.120)
    + check Ayalon 1995
        * Salīm Sarkīs authored his journal *al-Mushīr* all by himself, warned readers that during an illness he would not be able to respond to letters ({Ayalon 1995@224})
    + implicit assumption:
        * Seikaly reads all articles in *al-Muqtabas* as Kurd ʿAlī's work
- the newspaper *al-Muqtabas* rejected allegations that articles published by pseudonymous authors were indeed authored by the editors. Instead, the claim, not all *ʿulamāʾ* and *udabāʾ* in support of progress can speak out.{jarmuq 51@3}


### editors / publishers being absent from place of publication

- Ayalon provides examples of journals informing their readers that due to absences of their publishers, they will have to publish double issues ({Ayalon 1995@224})
    + *al-Hilāl*, 15 May 1900, p.508
    + *al-Muqtabas*, 6(4) (May 1911), back cover (all three copies I had access to were missing back covers)

- [*al-Zuhūr* 1(7):368](journal_al-zuhur/tei/oclc_1034545644-i_7.TEIP5.xml#div_1.d2e2020) apologises to its readers for the delay in publishing this issue because the editor was travelling outside Egypt/Cairo
- Muḥammad Kurd ʿAlī is repeatedly absent from Damascus
    + during times of exile, he writes long letters, which are then used to fill the pages of the journal once he returned to Damascus.
    + 1909, 15 October - 1910
        * the newspaper *al-Muqtabas*: suspended between 20 September 1909 and 9 March 1910
        * the journal *al-Muqtabas*:
            - an article in [no. 4(2)](https://github.com/tillgrallert/digital-muqtabas/blob/master/xml/oclc_4770057679-i_38.TEIP5.xml#div_25.d1e4565) scheduled for February/March 1909 was referenced in the newspaper [*al-Quds* #60 of 11 June 1909, p.4 ({al-quds-1-60@4})](http://www.palestine.mei.columbia.edu/alquds-issues/2017/2/21/issue-60).
            - no. 4(7) is only published in the first week of April 1910
        * Kurd ʿAlī escapes his arrest
        * writing *gharāʾib al-gharb*
            - according to my count 35 letters, first published in the newspaper?
            - published in the journal *al-Muqtabas* [no. 4(8)](digital-muqtabas/xml/oclc_4770057679-i_43.TEIP5.xml#div_3.d1e692), [4(9)](digital-muqtabas/xml/oclc_4770057679-i_44.TEIP5.xml#div_3.d1e690), [4(10)](digital-muqtabas/xml/oclc_4770057679-i_45.TEIP5.xml#div_7.d1e1693), [4(11)](digital-muqtabas/xml/oclc_4770057679-i_46.TEIP5.xml#div_8.d1e1619), [4(12)](digital-muqtabas/xml/oclc_4770057679-i_47.TEIP5.xml#div_7.d1e3096) and [5(1)](digital-muqtabas/xml/oclc_4770057679-i_48.TEIP5.xml#div_8.d1e3262)
    + 1912, 27 April -
        * the newspaper *al-Muqtabas* is suspended between 18 April and 8 August 1912
        * this is NOT when he wrote *gharāʾib al-gharb*. Instead his reports were published in the journal, starting with no 8(1) as *fī diyār al-gharb*
            - published in the journal *al-Muqtabas*, claiming that about 40 letters had been published in the newspapers *al-Qabas* and *al-Muqtabas*, No.s [8(1)](digital-muqtabas/xml/oclc_4770057679-i_84.TEIP5.xml#div_7.d1e1996), [8(2)](), [8(3)](digital-muqtabas/xml/oclc_4770057679-i_86.TEIP5.xml#div_4.d2e2317), [8(4)](digital-muqtabas/xml/oclc_4770057679-i_87.TEIP5.xml#div_7.d1e1729), [8(5)](digital-muqtabas/xml/oclc_4770057679-i_88.TEIP5.xml#div_6.d1e1213), [8(6)](digital-muqtabas/xml/oclc_4770057679-i_89.TEIP5.xml#div_9.d1e1969), [8(7)](digital-muqtabas/xml/oclc_4770057679-i_90.TEIP5.xml#div_7.d1e1254)
        + >Only one month later, *al-Muqtabas* was banned from publication and an attempt was made to arrest Muḥammad Kurd ʿAlī over the re-print of a *qaṣīda* by Shaykh Ibrāhīm al-Uskūbī that had been previously published in the two Beiruti papers of *al-Waṭan* and *al-Balagh* without any repercussion from the censors. However, Muḥammad Kurd ʿAlī was seemingly warned by the arrest party itself and managed to escape to Egypt; his brother Aḥmad was arrested in his stead. While at large, Muḥammad Kurd ʿAlī was accused of having formed a secret society with the purpose of overthrowing the Caliphate and charged with high treason, while the authorities in Beirut suspended *al-Balagh* from publication.[^1]

        + >Muḥammad Kurd ʿAlī published the first account of these events in the journal *al-Muqtabas* directly after his flight to Cairo; [{KurdʿAlī 1912}](). According to this account the attempted arrest took place on 17 April 1912.
        + As a consequence, the publication of the journal *al-Muqtabas* moved to Cairo with [No. 7(6)](https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_77.TEIP5.xml).[^2]
        + *al-Muqtabas* 8(1):2 notes that the publication of this volume was delayed by Muḥammad Kurd ʿAlī being in Europe for the first three months (of the year). With this volume publication moved back to Damascus.
        + **TO DO**: change place of publication for 7(6--12) to Cairo
    - In March 1914, Muḥammad Kurd ʿAlī signs articles "From Constantinople"; {muqtabas 626-eap}

[^2]: [*al-Muqtabas* 7(6):496](digital-muqtabas/xml/oclc_4770057679-i_77.TEIP5.xml#div_14.d1e4462)

[^1]: {Devey 1912e; Devey 1912f}{KurdʿAlī 1928@417}{Devey 1912g}

## format of publication

- library copies
    + [*al-Zuḥūr* 2(1):13](journal_al-zuhur/tei/oclc_1034545644-i_12.TEIP5.xml#p_2.d2e476) announces that the first volume is available in bound library copies at the office in Cairo

## mode of production

- Ayalon claims that "the team normally consist[ed] of the owner (*sahib al-imtiyaz*, or licensee) and one or two assistants." ({Ayalon 1995@224-225})
- *Thamarāt al-Funūn* asked readers to address letters to one (!) of its editors, Aḥmad Ḥasan Ṭabbāra, 1908. The newspaper doesn't list anyone else in its masthead ({tf-oib 1655@1}).
- *al-Iqbāl* recorded ʿAbd al-Bāsiṭ al-Unsī as owner and editor-in-chief and Muḥiyī al-Dīn al-Khayyāt as "one of its editors" in 1908; ({iqbal 35-260@1})
- *al-Bashīr* did not mention a person in its masthead in 1908, but recorded "The Catholic Press" and Yūsuf Kīrīn at the bottom of the last page; ({bashir 39-1872@4})
- *al-Ittiḥād al-ʿUthmānī* recorded only Aḥmad Ḥasan Ṭabbāra as the owner (*ṣāḥib*); {ittihad-1-33@1}
- the newspaper *al-Muqtabas* began listing a *mudīr masʾūl* (Aḥmad Kurd ʿAlī) on 26 April 1910; {muqtabas 86-eap@1 }

## necessity of studies of the ideosphere

- Zachs 2018: Debates on Women’s Suffrage in the Arab Press, 1890-1914
    + methodology!!!!!
        - how can one illustrate a "debate" in earnest using two periodical articles 12 years apart without any comment on this distance?
        - a "debate" cannot be (re-)constructed by picking random articles with "woman" in the title from four random periodicals over the course of 40 years
        - one would need to talk about differences between British Egypt and Ottoman Syria

## editors' knowledge of their own periodicals

- Muḥammad Kurd ʿAlī makes false references to his journal *al-Muqtabas* in *Khiṭaṭ al-Shām*.
    + on pp.83--85 he claims to quote verbatim from volume 6. But some parts of this text could only be located in [no. 5(5)](oclc_4770057679-i_52.TEIP5.xml#div_12.d1e2991)

# 1. Methodological notes
## our corpus

| publication.title | publication.id.oclc | volume.count | issue.count | article.count | article.count.is.independent | article.count.has.author | word.count | character.count | words.per.article | characters.per.article | characters.per.word |
|-------------------|---------------------|--------------|-------------|---------------|------------------------------|--------------------------|------------|-----------------|-------------------|------------------------|---------------------|
| al-Ḥaqāʾiq        |           644997575 |            3 |          35 |           389 |                          257 |                      163 |     298090 |         1316142 |  832.660484848951 |       3681.46603402433 |    4.42336130476421 |
| al-Ḥasnāʾ         |           792756327 |            1 |          11 |           173 |                          136 |                       63 |       1421 |            5988 |  8.29124776931973 |       35.3379624037901 |    4.29100836427165 |
| al-Manār          |             1588981 |           12 |         139 |          1114 |                         1114 |                        0 |    2187318 |         9908975 |  2076.95105879333 |       9403.27597863767 |    4.52681168661136 |
| al-Muqtabas       |          4770057679 |            9 |          96 |          2964 |                          792 |                      377 |    1981081 |         8953867 |  873.341307920755 |       3938.47737955481 |    4.51753515150654 |
| Lughat al-ʿArab   |           472450345 |            3 |          34 |           939 |                          330 |                      152 |     373832 |         1638225 |  485.206043680748 |       2132.43872149233 |    4.39265321063476 |



## network of authors

+ questions:
    * what are the most important authors?
        - evaluated by number of articles and journals they published in.
    * what is the reach of journals?
        - indicated by locations of writing provided in bylines etc.
+ required data/ approach
    * bibliographic data on the article level
    * full text for stlometric analysis
+ data sets:
    * OpenArabicPE: semi-automatic mark-up
        - *al-Muqtabas*
        - *al-Ḥaqāʾiq*
        - *Lughat al-ʿArab*: 34 issues before the gap in publication between 1912 and 1926
        - *al-Manār*: volumes 9 to 20 from 1906 onwards until the end of October 1918
            + this subset overlaps with *al-Muqtabas* in order to avoid a heavy bias towards *al-Manār*
        - *al-Ḥasnāʾ*
    * Sakhrit (cut-off after 1920)
        -
+ problems
    * general issue: disambiguation of personal names and toponyms
    * originals: bylines frequently missing
    * OpenArabicPE
    * Sakhrit
        - no full text editions
        - unknown origin and quality of bibliographic metadata
        - *main issue*: false negatives
        - publication dates cannot be trusted

### network of authors in four journals

1. data set:
    - *al-Muqtabas*: 96 issues
    - *al-Ḥaqāʾiq*: 35 issues
    - *Lughat al-ʿArab*: 34 issues before the gap in publication between 1912 and 1926
    - *al-Ḥasnāʾ*: 12 issues
2. results: 2019-09-27
    - number of authors
        + OAPE
            * total: 319
            * authors in
                - 4 journals: 1
                - 3 journals: 0
                - 2 journals: 13
                - 1 journal: 305
        + *al-Muqtabas*
            - total: 139
            - with VIAF ID: 65
            - average birth year: 1869
        + *al-Ḥaqāʾiq*
            - total: 103
            - with VIAF ID: 15
            - average birth year: 1837
        + *Lughat al-ʿArab*
            - total: 52
            - with VIAF ID: 12
            - average birth year: 1875
        + *al-Ḥasnāʾ*
            - total: 42
            - with VIAF ID: 6
            - average birth year: 1883

|      journal      | number of authors | authors in VIAF | average year of birth |
|-------------------|-------------------|-----------------|-----------------------|
| *al-Muqtabas*     |               139 |              65 |                  1869 |
| *al-Ḥaqāʾiq*      |               103 |              15 |                  1837 |
| *Lughat al-ʿArab* |                52 |              12 |                  1875 |
| *al-Ḥasnāʾ*       |                42 |               6 |                  1883 |

| rank |                author.id.viaf                |      author.name      | author.name.transliterated | author.birth | author.death | journal.count | article.count | word.count | Ayalon 1995 |
|------|----------------------------------------------|-----------------------|----------------------------|--------------|--------------|---------------|---------------|------------|-------------|
|    1 | [14924300](https://viaf.org/viaf/14924300)   | معروف  الرصافي        | m3rwf  alrSafy             | 1875         | 1945         |             4 |            31 |      15038 | n           |
|    2 | NA                                           | كاظم   الدجيلي        | kaZm   aldjyly             | 1884         | 1970         |             2 |            28 |      38050 | n           |
|    3 | NA                                           | إبراهيم  حلمي  العمر  | abrahym  7lmy  al3mr       | 1890         | 1942         |             2 |            22 |      40747 | n           |
|    4 | [40250618](https://viaf.org/viaf/40250618)   | عيسى  اسكندر  المعلوف | 3ysA  askndr  alm3lwf      | 1869         | 1956         |             2 |            22 |      23383 | passing     |
|    5 | [39370998](https://viaf.org/viaf/39370998)   | ساتسنا                | satsna                     | 1866         | 1947         |             2 |            15 |      20106 | n           |
|    6 | [22006374](https://viaf.org/viaf/22006374)   | محمد  رضا  الشبيبي    | m7md  rDa  alWbyby         | 1889         | 1965         |             2 |            12 |      24156 | n           |
|    7 | NA                                           | محمد  الهاشمي         | m7md  alhaWmy              | NA           | NA           |             2 |             6 |       2717 | n           |
|    8 | [236524859](https://viaf.org/viaf/236524859) | مصطفى  صادق  الرافعي  | mSTfA  SadQ  alraf3y       | 1880         | 1937         |             2 |             6 |       3711 | passing     |
|    9 | NA                                           | محمد  باقر  الشبيبي   | m7md  baQr  alWbyby        | 1889         | 1960         |             2 |             5 |       3331 | n           |
|   10 | NA                                           | أبو الضيا             | abw alDya                  | NA           | NA           |             2 |             4 |       5836 | n           |
|   11 | [60500457](https://viaf.org/viaf/60500457)   | أحمد  محرم            | a7md  m7rm                 | 1877         | 1945         |             2 |             4 |       1543 | n           |
|   12 | NA                                           | ا. ج                  | a. j                       | NA           | NA           |             2 |             3 |        639 | n           |
|   13 | [63117968](https://viaf.org/viaf/63117968)   | محمد  راغب  طباخ      | m7md  raGb  TbaK           | 1877         | 1951         |             2 |             3 |       2633 | n           |
|   14 | [36771043](https://viaf.org/viaf/36771043)   | ولي الدين   يكن       | wly aldyn   ykn            | 1873         | 1921         |             2 |             2 |        795 | n           |

Table: authors that published in more than one journal in our corpus comprising *al-Ḥaqāʾiq*, *al-Ḥasnāʾ*, *Lughat al-ʿArab* and *al-Muqtabas*


## network of texts referenced

+ questions:
    * what did people read?
        - culling bibliographic data from review sections
    * what are the most important periodicals?
        - number of articles and journals that reference a specific periodical
+ required data
    * full text editions with mark-up of referenced texts
    * The mark-up is done semi-automatically with [XSLT](https://github.com/OpenArabicPE/tools/blob/master/xslt/tei_mark-up-references-to-periodicals.xsl) utilising regular expressions. Afterwards one needs to manually check the marked-up strings for obvious errors.
+ data sets:
    * OpenArabicPE
        - *al-Muqtabas*
        - *al-Ḥaqāʾiq*
        - *Lughat al-ʿArab*: first three volumes,
        - *al-Manār*: first 20 volumes, has not been incorporated into the analysis yet
        - *al-Ḥasnāʾ*
+ processing data
    * an [XSLT stylesheet](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/xslt/tei_statistics.xsl) gathers statistics from TEI XML input and writes CSV to `oclc_\d+.*-i_\d+-stats_tei-referenced-periodicals.csv`
    * This input is processed with [R](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/r/oape_process-data.R), which combines the individual CSV files into a single data frame. Output is saved as `oape_referenced-periodicals.rda` and `oape_referenced-periodicals.csv`
        - necessary information for mapping the network
            1. source
                - title
                    + Arabic
                    + IJMES
                - ID: OCLC
                - publication place
                    + name
                        * original
                        * IJMES
                    + ID: GeoNames
                    + coordinates
            2. target
                - title
                    + original / Arabic
                    + IJMES
                - ID: OCLC
                - publication place
                    + name
                        * original
                        * IJMES
                    + ID: GeoNames
                    + coordinates
            3. weight
                - number of articles
                - number of issues
        - the necessary information for mapping can be done by left and right joins in R
    * The network of periodicals is then plotted using another [R script](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/r/oape_network-analysis.R)
    * load edges table into Gephi and compute various network statistics

## 2019-08-16

1. data set
    - referenced periodicals from four titles (al-Muqtabas, Lughat al-ʿArab, al-Ḥasnāʾ, and al-Ḥaqāʾiq)
        - 423 different periodical titles?
2. settings in Gephi
    - nodes:
        + size: weighted in-degree, 20-120
        + colour: in-degree
2. general observations
    1. all journals are self-referencial, they are the main source of references to themselves
    2. the vast majority of periodicals (90,33 % or 387 titles) are referred to by only a single journal. 313 periodicals are only mentioned in a single issue and 311 in a single article.
1. network of referenced periodicals *per article*: 465 periodicals
    - in-degree (per journal): **need updating**
        + 1: 90,33 % or 387 periodicals
        + 2: 7,55 % or 31 periodicals
        + 3: 1,18 % or 5 periodicals
            1. *al-Muqtabas*
            * *al-Hilāl*
            * *al-Manār*
            * *al-Muqtaṭaf*
            * *al-Mufīd*
2. network of referenced periodicals *per issue*: 465 periodicals
    - in-degree (per journal):
        + 1: 90,54 % or 421 periodicals
        + 2: 8,17 % or 38 periodicals
        + 3: 1,29 % or 6 periodicals
            1. *al-Muqtabas*
            * *al-Hilāl*
            * *al-Manār*
            * *al-Muqtaṭaf*
            * *al-Ḍiyā*
            * *al-Mufīd*
    - after cleaning (Gephi)
        + 1: 90,54 % or 421 periodicals
        + 2: 8,17 % or 35 periodicals
        + 3: 2,13 % or 9 periodicals
            1. *al-Muqtabas*
            * *al-Hilāl*
            * *al-Manār*
            * *al-Muqtaṭaf*
            * *al-Ḍiyā*
            * *al-Mufīd*
            * *al-Watan*
            * *al-Haqīqa*
            * *al-Ḥuqūq*
    - *al-Ḍiyāʾ*
        + in 1913, *al-Ḥaqāʾiq* mentions two specific articles on the Arabic language
        + in *al-Muqtabas* it is mostly in the form of "the publisher of *al-Ḍiyāʾ"
            * some references to articles in *al-Diyāʾ* long after its publication
            * one in 1906 as a readers' digest
        + in *lughat al-ʿArab*: one historical reference
3. number of referenced periodicals per journal
    1. *al-Manār* (1588981): 206
    2. *al-Muqtabas* (4770057679): 404 **BUT** this counts numerous periodicals twice due to *al-Muqtabas* being published in Cairo and Damascus.
    3.

# 2. Where is everything

1. data
    - git repository for all the analytical questions at [`/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis`](https://github.com/openarabicpe/OpenArabicPE_analysis). It is **important** to add the material referenced in the paper to the repository of this paper to avoid issues with erroneous cross-linking of visualisations and data sets.
        - bibliographic data
        - plain text files for stylometric analysis
        - xslt and R scripts
        - statistics as CSV and RData files
        - visualisations
2. writing / drafts
    - git repository for the 2018 conference paper and other writing at [`/BachUni/publications/github/p3a6afa20`](https://github.com/tillgrallert/p3a6afa20)
3. additional notes
    - a text file with my notes on stylometry at [`/BachUni/BachBibliothek/NotationalVelocityLib/stylometry- OpenArabicPE.txt`](/BachUni/BachBibliothek/NotationalVelocityLib/stylometry- OpenArabicPE.txt)
4. literature
    1. in Sente: I have organised literature in Sente using tags
        - `Paper: authorship`
            + currently only one reference
        - `Project: OpenArabicPE`
    1. subject:
        - **Arabic press**: I have a good overview and have pretty much read everything there is on this matter
        - **nahḍa**: I have a rather rudimentary overview
        - **digitised newspapers**:
        - **OCR**: some limited literature on the issue of OCR for Arabic
            + I can reference them all
    2. methodology:
        - **bibliometry**: do I need this?
        - **stylometry**: I have read a number of articles
            + can I explain my methodology?
        - **social network analysis**: I have not read a lot on this but I am able to do it
            + can I interpret my own results?

# Biographical notes

There are family relations between the Qāsimīs in the two journals

Jamāl al-Dīn al-Qāsimi (*al-Muqtabas*) and Muḥammad al-Qāsimī (al-Ḥallāq)

## Maʿrūf al-Ruṣāfī (1875--1945)

- Sources:
    + [{Ziriklī 1979f@268-269}](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_7.TEIP5.xml#div_1301.d2e59460)
    +  VIAF [14924300](https://viaf.org/viaf/14924300)

Arabist, **poet**, journalist, politician. Born in Baghdad, dropped out of the military *rüşdiye* school and continued his studies with Maḥmūd Shukrī al-Alūsī. Worked as a **teacher** in Baghdad before he moved to Istanbul after the Young Turk Revolution, where he worked as Arabic teacher at the "Royal College" and at the newspaper *Sabīl al-Rashad*---a move that is well reflected in *al-Muqtabas*. He was elected MP for al-Muthanna (Iraq) in 1912 and 1914. After WWI he became member of the **Arab Scientific Academy**, established by Muḥammad Kurd ʿAlī in Damascus.

- works
    + *Dīwān Maʿrūf al-Ruṣāfī*
        * OA from [Hindawi](https://www.hindawi.org/books/51703160/)
        * from [shamela](http://shamela.ws/rep.php/book/4427)
        * individual *qaṣāʾid* from [adab.com](http://www.adab.com/modules.php?name=Sh3er&doWhat=lsq&shid=301)
        * **1910**, *Dīwān al-Ruṣāfī: wa-huwa majmūʿ mā naẓamahu al-shāʿir al-ijtimāʿī al-kabīr Maʿrūf Efendi al-Ruṣāfī al-Baghdādī*, edited by Muḥī al-Dīn al-Khayyāṭ and Muṣṭafā Ghalāyīnī, Bayrūt: al-Maktaba al-Ahliyya, 1910 (1328 aH).
            - [worldcat](https://www.worldcat.org/oclc/4770928968) claims 1903 as publication date,
            - but articles in the Beiruti press suggest 1910 as the correct publication date.
        - the announcement in *al-Muqtabas* is bombastic. The paper claims that al-Ruṣāfī is known among some people as the "poet of *al-Muqtabas*" and wrongly adds that "more than three quarters [of the *qaṣāʾid* therein] had been published in this journal". *al-Muqtabas* 4(10), p.620
- to do: check if the qaṣīdas printed in magazines were taken from the *Dīwān*
    + some of them can be found in the Hindawi edition of the *Dīwān* but were they part of the original majmūʿ


## Kaẓim al-Dujaylī (1884--1970)

- Sources:
    + [{Ziriklī 1979@215}](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_5.TEIP5.xml#div_1205.d2e46580)
    + VIAF: none

- Iraqi **poet** from the village of Samīka west of Baghdad. Student of Maḥmūd Shukrī al-Alūsī and Anastās Mārī al-Karmalī
- **journalist**: Co-publisher of *Lughat al-ʿArab*
- Law school graduate after WWI
- member of the **Arab Scientific Academy** in Damascus (from 1922 onwards)
- professor / **teacher** of Arabic at the University of London (1924 onwards)

## Ibrāhīm Ḥilmī al-ʿAmr (1890--1942)

- Sources:
    + [{Ziriklī 1979a@37}](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_1.TEIP5.xml#div_96.d2e4166)
    + VIAF: none
    + texts themselves: signed as student
- Iraqi author, gained fame as author of letters to journals in Syria and Egypt before WWI
- established the newspaper *al-Nahḍa* in Baghdad in 1913
- he worked with the Ottomans during WWI and they brought him to Damascus in the final days of the war
- Collaborated on the newspaper *Lisān al-ʿArab* in Damascus after WWI

## ʿĪsā Iskandar al-Maʿlūf (1869--1956)

- Sources
    + [{Ziriklī 1979@101}]
    + VIAF [40250618](https://viaf.org/viaf/40250618)

- **journalist**

Born in the village of Kafr ʿAqqāb in Mt. Lebnon.  Educated across Lebanon and in the Greek Orthodox school in Damascus. Co-editor of the periodicals *Lubnān*, *al-ʿAṣr al-Jadīd* and *al-Niʿma*. In 1911 he established the journal *al-Āthār* (published only 5 volumes){>> in Zaḥle<<}. Collector of books and manuscripts: AUB holds some 500 manuscripts from his private collection.
After WWI he became member of the **Arab Scientific Academy**, established by Muḥammad Kurd ʿAlī in Damascus.

## Buṭrus bin Jibrāʾīl Yūsuf ʿAwwād, Father Anastās Mārī al-Karmalī, Sātisnā (1866--1947)

- Sources
    + [{Ziriklī 1979b@25-26}]
    + VIAF: [39370998](https://viaf.org/viaf/39370998)

Buṭrus bin Jibrāʾīl Yūsuf ʿAwwād, commonly known as Father Anastās Mārī al-Karmalī and writing under  the pen name Sātisnā

Carmelite priest and Arabic linguist. His father was from Mt. Lebanon and moved to Baghdad, where he married. Buṭrus studied at religious schools, moved to Beirut in 1886 to study at the Jesuit college and continued his studies in Liege (Belgium) and Montpellier (France). Remained in France at least until the mid-1890s, where he was ordained a priest, before he returned to Baghdad. Prolific writer and contributor to periodicals under various pen names. He published his own philological journal, *Lughat al-ʿArab*, from 1911 onwards.

## Muḥammad Riḍā al-Shabībī (1889--1965)

- Sources:
    + [{Ziriklī 1979e@127}](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_6.TEIP5.xml#div_672.d2e32532)
    + VIAF: [22006374](https://viaf.org/viaf/22006374)
- Iraqi **poet**, statesman and educator
- born in Najaf
- member of the **Arab Scientific Academy** in Damascus
    + as well as the academies in Cairo and Baghdad
- >He was elected president of the Iraqi Academy in 1928–1929 and in the 1930s became a member of the Arabic Language Academy in Cairo (Wikipedia)

## Muḥammad al-Hāshimī

- Sources: none

## Muṣṭafā Ṣādiq al-Rāfiʿī (1880--1937)

- Sources
    + [{Ziriklī 1979f@235}]
    + VIAF [236524859](https://viaf.org/viaf/236524859)
- Famous deaf Egyptian **poet** from Tanta. One of the most famous Arabic poets of the early twentieth century
- author of the Egyptian national anthem between 1923--1936.

## Muḥammad Bāqir al-Shabībī (1889--1960)

- Sources
    + [{Ziriklī 1979e@49}](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_6.TEIP5.xml#div_236.d2e11574)
    + VIAF: **none**

- Iraqi **poet** from Najaf
- brother of Muḥammad Riḍā al-Shabībī
- **journalist**: established the newspaper weekly *al-Furāt* in 1339 aH (only five issues published)
- **politician**: MP for Liwā al-Muntafak 1930--54

## Abū al-Ḍiyāʾ

## Aḥmad Muḥarram (1877--1945)

- Sources
    + [{Ziriklī 1979a@202}]
    + VIAF [60500457](https://viaf.org/viaf/60500457)
- Egyptian **poet** from the Muḥafaẓa of al-Buḥayra

## Muḥammad Rāghib Ṭabbākh (1877--1951)

- Sources
    + {Ziriklī 1979e@123-124}
    + VIAF [63117968](https://viaf.org/viaf/63117968)

- born and died in Aleppo
- shaykh, ḥāfiẓ
- educated in the Ottoman ibtidāʾiyya
- **educator**: established numerous schools in Aleppo

## Walī al-Dīn Yakan (1873--1921)

- Sources
    + [{Ziriklī 1979g@118}](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_8.TEIP5.xml#div_634.d2e23341)
    + VIAF [36771043](https://viaf.org/viaf/36771043)

- Egyptian **poet**
    + published in *al-Muqattam*
- born in **Istanbul** but his father was posted to Cairo soon thereafter
    - Turkish father and Circassian mother
- Ottoman bureaucrat until 1908
- 1908: return to Egypt



## Muqtabas

The four men out of the five, for which we can find biographical records, are in many aspects exemplary of the modernising late Ottoman Empire and the Middle East: Coming from a plurality of religious and social backgrounds---Greek Orthodox, Catholic and Sunnī Muslim, priest and leading Salafi thinker of the second generation, part-time officials, of simple means and members of the old elites---they belonged to the same generation (born between the mid-1860s and mid-1870s){-- and worked as journalists, teachers, and occasionally politicians. All of them--}, were highly mobile and well-travelled and had good command of local as well as foreign languages{>> to the extent that some of them published translations<<}.

Those four out of the five men for which we can retrieve matching records from VIAF, belonged to the same generation (born between the mid-1860s and mid-1870s) and were prolific authors (judged by the numbers of published works in VIAF). However, by the latter metric, many other authors were just as, if not more, important: Shakīb Arslān (rank: 12), Amīn Rīḥānī (30), Muḥibb al-Dīn al-Khaṭīb (20), Aḥmad Taymūr (6), Aḥmad Zakkī (6), Aḥmad Shawqī (52).

A further look at the four biographies reveals a telling plurality of social and religious backgrounds:


### Yūsuf Jirjis Zakham (1880--?)

Yūsuf Jirjis Zakham signed a number of articles in *al-Muqtabas* and other publications. He also provided a number of locations in Nebraska as places of writing. It is difficult to establish the anglicised version of his name, but there are numerous members of the Zakem family in Nebraska in the early 20th century. **Joseph George** can be assumed as his forenames.

He was born between 1880-01-07 (1920 census), 1880-04-20 (1910) and 1881-01-06 (1920 census)

- Naturalisation papers are available for **Joseph George Zakem**, born on 14 May 1880 in Syria, and married to Myra Zakem from the [Lincoln-Lancaster County Genealogical Society](http://www.llcgs.net/getnaturalize.php?id=J258).
- **J. E. Zakem** can be found in the [1910 US Federal Census](https://www.familysearch.org/ark:/61903/1:1:ML42-G7Q) as living in Ward 1, Lincoln, Lancaster, Nebraska
    + transcription from sheet is wrong: J.G. Zakem
    + data recorded on 1910-04-19
    + aged 29, born in Turkey, Assyrian
    + both parents from Turkey, Assyrian
    + immigrated to US in 1902, no information naturalisation
    + speaks English
    + trade/profession: correspondant
    + industry: newspaper
    + all members of his household know how to read and write
    + married to Myra Zakem, from Iowa, aged 21
    + they had three lodgers from Turkey
        * Addad Zakem, aged 32,
            + 1895: immigrated to US
            + keeper of a café
        * Emely Zakem, aged 21
            - 1907: immigrated to US
        * Emely Zakem, aged 21
            - 1907: immigrated to US
            - waitress at café
- **Joseph G Jakem** [sic] can be found in the [1920 US Federal Census](https://www.familysearch.org/ark:/61903/1:1:MCKV-NXW) as living in Ward 7, Lincoln, Lancaster, Nebraska
    - The data was recorded on 1920-01-06
    - born in 1880 (aged 39), married to Myra M Jakem [sic], aged 29, born in Iowa, who can read and write
        - her father was from Michigan
    - 1902: immigration to the US
    - 1904: naturalisation
    - children
        - Rose Ellen, 8
        - George G., 6
        - Ruth, 4 10/12
        - Mitchell E., 2 11/12
+ **Joseph G Zackem** can be found in the [1930 US Federal Census](https://www.familysearch.org/ark:/61903/1:1:XQKB-3V4) as living in Ward 5, Lincoln, Lancaster, Nebraska. He was born in 1882 and aged 27 at first marriage.
    * data was recorded on 1930-04-09 amd 1930-04-10
    * aged 48, born in Syria
    * immigrated to the US in 1904, no info on naturalisation
    * occupation: Rug dealer, Oriental Goods
    * owns his home, which is valued at 10.000 USD
    * married to Myrah, ageed 40, born in Iowa
    * children
        - Rosalla, 18, working as a sales ladie in a Department Store
        - George J, 16
        - Ruth J, 15
        - Michael R., 13
        - Josef G, Jr, 9
+ **Joseph G Zaken** can be found in the [1940 US Federal Census](https://www.familysearch.org/ark:/61903/1:1:K997-KT2) as living in Ward9, Omaha City, Douglas, Nebraska
    * data was recorded on 1940-04-02
    + aged 61, born in Syria

- Nebraska Census records are available [here](https://www.accessgenealogy.com/census/nebraska-census-records.htm)

### Jamāl al-Dīn al-Qāsimī (1866--1914)

Damascene notable and Sunni scholar. Travelled to Egypt in 1312 aH. Opened a school in Damascus that was shut down by the Vali in 1313 aH. Taught in his family home. Prolific contributor to newspapers and journals. 72 book manuscripts

## Ḥaqāʾiq

The picture is different for *al-Ḥaqāʾiq*, which was repeatedly in conflict with *al-Muqtabas* over the latter's supposed moral laxity. Its most prolific contributors were Damascene Sunni religious scholars from notable families, many of whom were at least one generation older than its opponents, e.g. Ibrāhīm Mardam Bek, Muḥammad ʿĀrif al-Munīr al-Ḥusaynī (b.1847/48), Mukhtār al-Muʾayyad (b.1822) and Muḥammad al-Qāsimī (b.1843), whose son Jamāl al-Dīn al-Qāsimī published in *al-Muqtabas*. Against this backdrop the initially surprising finding of practically no overlap between the two networks of authors published in journals from the same city, becomes less so (Fig. 5).

Ibrāhīm Mardam Bek, Muḥammad Farīd Wajdī (1875--1954), Muḥammad ʿĀrif al-Munīr al-Ḥusaynī (1847--), ʿAbd al-Rahmān al-Qaṣṣār (1863--1931), Muḥammad al-Qāsimī (al-Ḥallāq, 1843--1900), Ṣāliḥ al-Sharīf (1869--1920), Mukhtār al-Muʾayyad (1822--1921)

### Muḥammad Farīd Wajdī (1875--1954)

- ({Ziriklī 1979e@329})

Born in Alexandria, moved to Damietta and Suez, died in Cairo. Published the journal *al-Ḥayyāt* in Suez. Wrote at least some of his books in French. Moved to Cairo, where he published the daily newspaper *al-Dustur* for some period before he established the weekly *al-Wajdiyāt*. Became one of the editors of *al-Azhar*

### Muḥammad ʿĀrif al-Munīr al-Ḥusaynī (1848--1923)

Damascene Shafīʿī jurisprudent. Born and died in Damascus.

### ʿAbd al-Rahmān al-Qaṣṣār (1863--1931)

Born and died in Damascus.

### Muḥammad al-Qāsimī al-Ḥallāq (1843--1900)

Damascene ʿālim. Father of Jamāl al-Dīn al-Qāsimī. knowledgeable about Damascene crafts

### ʿAbd al-Qādir al-Iskandarānī (1875--1943)

Son of Muḥammad Salīm al-Kaylānī. Born in ALexandria but lived and worked in Damascus. He was an ʿālim who studied at the Umayyad Mosque and authored a number of tractates (*rasāʾil*) according to VIAF.

### Abū al-Ḍiyā Tawfīq Bey (1849--1913)

An Ottoman **journalist**, who was born and died in Istanbul.

in our corpus, a certain "Abū al-Ḍiyāʾ" signes articles from Damascus. This would be somebody else!
