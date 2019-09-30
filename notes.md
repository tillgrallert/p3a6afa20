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
    + number of works in worldcat
- make TEI bibliography of the most referenced periodicals (minimum 2 journals in my corpus): currently 36 titles
    + **done**
    + **done**: write XSLT to enrich bibliography and link `<title>`s to bibliography
    + **done**: improve CSV of referenced periodicals

# 1. Methodological notes
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
    - 423 different periodical titles
2. general observations
    1. all journals are self-referencial, they are the main source of references to themselves
    2. the vast majority of periodicals (90,33 % or 387 titles) are referred to by only a single journal. 313 periodicals are only mentioned in a single issue and 311 in a single article.
1. network of referenced periodicals *per article*
    - in-degree (per journal):
        + 1: 90,33 % or 387 periodicals
        + 2: 7,55 % or 31 periodicals
        + 3: 1,18 % or 5 periodicals
            1. *al-Muqtabas*
            * *al-Hilāl*
            * *al-Manār*
            * *al-Muqtaṭaf*
            * *al-Mufīd*
2. network of referenced periodicals *per issue*
    - in-degree (per journal):
        + 1: 90,33 % or 387 periodicals
        + 2: 7,55 % or 31 periodicals
        + 3: 1,18 % or 5 periodicals
            1. *al-Muqtabas*
            * *al-Hilāl*
            * *al-Manār*
            * *al-Muqtaṭaf*
            * *al-Mufīd*

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
    + [Ziriklī 7:268-269](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_7.TEIP5.xml#div_1301.d2e59460)
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
    + [Ziriklī 5:215](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_5.TEIP5.xml#div_1205.d2e46580)
    + VIAF: none

- Iraqi **poet** from the village of Samīka west of Baghdad. Student of Maḥmūd Shukrī al-Alūsī and Anastās Mārī al-Karmalī
- **journalist**: Co-publisher of *Lughat al-ʿArab*
- Law school graduate after WWI
- member of the **Arab Scientific Academy** in Damascus (from 1922 onwards)
- professor / **teacher** of Arabic at the University of London (1924 onwards)

## Ibrāhīm Ḥilmī al-ʿAmr (1890--1942)

- Sources:
    + [Ziriklī 1:37](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_1.TEIP5.xml#div_96.d2e4166)
    + VIAF: none
    + texts themselves: signed as student
- Iraqi author, gained fame as author of letters to journals in Syria and Egypt before WWI
- established the newspaper *al-Nahḍa* in Baghdad in 1913
- he worked with the Ottomans during WWI and they brought him to Damascus in the final days of the war
- Collaborated on the newspaper *Lisān al-ʿArab* in Damascus after WWI

## ʿĪsā Iskandar al-Maʿlūf (1869--1956)

- Sources
    + [Ziriklī]
    + VIAF [40250618](https://viaf.org/viaf/40250618)

- **journalist**

Born in the village of Kafr ʿAqqāb in Mt. Lebnon.  Educated across Lebanon and in the Greek Orthodox school in Damascus. Co-editor of the periodicals *Lubnān*, *al-ʿAṣr al-Jadīd* and *al-Niʿma*. In 1911 he established the journal *al-Āthār* (published only 5 volumes){>> in Zaḥle<<}. Collector of books and manuscripts: AUB holds some 500 manuscripts from his private collection.
After WWI he became member of the **Arab Scientific Academy**, established by Muḥammad Kurd ʿAlī in Damascus.

## Sātisnā (1866--1947)

- Sources
    + [Ziriklī ]
    + VIAF

Buṭrus bin Jibrāʾīl Yūsuf ʿAwwād, commonly known as Father Anastās Mārī al-Karmalī and writing under  the pen name Sātisnā

Carmelite priest and Arabic linguist. His father was from Mt. Lebanon and moved to Baghdad, where he married. Buṭrus studied at religious schools, moved to Beirut in 1886 to study at the Jesuit college and continued his studies in Liege (Belgium) and Montpellier (France). Remained in France at least until the mid-1890s, where he was ordained a priest, before he returned to Baghdad. Prolific writer and contributor to periodicals under various pen names. He published his own philological journal, *Lughat al-ʿArab*, from 1911 onwards.

## Muḥammad Riḍā al-Shabībī (1889--1965)

- Sources:
    + [Ziriklī 6:127](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_6.TEIP5.xml#div_672.d2e32532)
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
    + [Ziriklī ]
    + VIAF [236524859](https://viaf.org/viaf/236524859)
- Famous deaf Egyptian **poet** from Tanta. One of the most famous Arabic poets of the early twentieth century
- author of the Egyptian national anthem between 1923--1936.

## Muḥammad Bāqir al-Shabībī (1889--1960)

- Sources
    + [Ziriklī 6:49](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_6.TEIP5.xml#div_236.d2e11574)
    + VIAF: **none**

- Iraqi **poet** from Najaf
- brother of Muḥammad Riḍā al-Shabībī
- **journalist**: established the newspaper weekly *al-Furāt* in 1339 aH (only five issues published)
- **politician**: MP for Liwā al-Muntafak 1930--54

## Abū al-Ḍiyāʾ

## Aḥmad Muḥarram (1877--1945)

- Sources
    + VIAF [60500457](https://viaf.org/viaf/60500457)
- Egyptian **poet** from the Muḥafaẓa of al-Buḥayra

## Muḥammad Rāghib Ṭabbākh (1877--1951)

- Sources
    + VIAF [63117968](https://viaf.org/viaf/63117968)

- born and died in Aleppo
- shaykh, ḥāfiẓ
- educated in the Ottoman ibtidāʾiyya
- **educator**: established numerous schools in Aleppo

## Walī al-Dīn Yakan (1873--1921)

- Sources
    + [Ziriklī 8:118](file:///BachUni/BachBibliothek/GitHub/TEI/oclc_165855925/tei/oclc_165855925-v_8.TEIP5.xml#div_634.d2e23341)
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

### Muḥammad Farīd Wajdī (1875--1954) (Ziriklī 6:329)

Born in Alexandria, moved to Damietta and Suez, died in Cairo. Published the journal *al-Ḥayyāt* in Suez. Wrote at least some of his books in French. Moved to Cairo, where he published the daily newspaper *al-Dustur* for some period before he established the weekly *al-Wajdiyāt*. Became one of the editors of *al-Azhar*

### Muḥammad ʿĀrif al-Munīr al-Ḥusaynī (1848--1923)

Damascene Shafīʿī jurisprudent. Born and died in Damascus.

### ʿAbd al-Rahmān al-Qaṣṣār (1863--1931)

Born and died in Damascus.

### Muḥammad al-Qāsimī al-Ḥallāq (1843--1900)

Damascene ʿālim. Father of Jamāl al-Dīn al-Qāsimī. knowledgeable about Damascene crafts

### ʿAbd al-Qādir al-Iskandarānī (1875--1943)

Son of Muḥammad Salīm al-Kaylānī. Born in ALexandria but lived and worked in Damascus. He was an ʿālim who studied at the Umayyad Mosque and authored a number of tractates (*rasāʾil*) according to VIAF.