---
title: "Catch me if you can! Attempts to track networks of authors and publication reviews in the wasteland of 'digitised' Arabic periodicals from the Ottoman Empire"
author: Till Grallert
date: 2018-09-11
ORCID: orcid.org/0000-0002-5739-8094
DOI: doi.org/10.5281/zenodo.1413610
licence: http://creativecommons.org/licenses/by-nd/4.0/
markdown: 
- pandoc
- CriticMarkup
include-after: <footer><span class="c_info c_license"><a rel="license" href="http://creativecommons.org/licenses/by-nd/4.0/"><img alt="Creative Commons Licence" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/4.0/88x31.png" /></a>This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nd/4.0/">Creative Commons Attribution-NoDerivatives 4.0 International License</a>.</span></footer>
---


<!-- # processing instructions -->
<!-- ## 1. HTML -->
<!-- pandoc -F pandoc-crossref -s -S -f markdown -t html5 --toc --include-in-header=/BachUni/programming/Pandoc/css-pandoc_online-publication.txt --include-in-header=/BachUni/programming/Pandoc/css-pandoc_code-highlight_oxygen-xml.txt --email-obfuscation=javascript catch-me-if-you-can.md -o index.html -->
<!-- ## 2. DOCX -->
<!-- pandoc -F pandoc-crossref -s -S -f markdown -t docx catch-me-if-you-can.md -o catch-me-if-you-can.docx -->

<div id="sec-badges" class="c_badges">
<!-- ORCID -->
[![ORCID](https://orcid.org/sites/default/files/images/orcid_16x16.png)](https://orcid.org/0000-0002-5739-8094)
<!-- licence -->
[![CC BY-ND 4.0](https://i.creativecommons.org/l/by-nd/4.0/88x31.png)](http://creativecommons.org/licenses/by-nd/4.0/)
<!-- release -->
[![GitHub release](https://img.shields.io/github/release/tillgrallert/p3a6afa20.svg)](https://github.com/tillgrallert/p3a6afa20/releases)
<!-- DOI -->
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1413610.svg)](https://doi.org/10.5281/zenodo.1413610)
</div>

# About {#sec-about}

>This is a draft paper to be presented at the Turkologentag 2018 in Bamberg, Germany, 19--21. September 2018.

>The current stable draft of this paper is version [v0.1](https://rawgit.com/tillgrallert/p3a6afa20/v0.1/index.html) and contains unprocessed references to sources and secondary literature, cross-references, and CriticMarkup. To comment / review / annotate this version via hypothes.is click [here](https://via.hypothes.is/https://rawgit.com/tillgrallert/p3a6afa20/v0.1/index.html). The most recent changes are available [here](https://tillgrallert.github.io/p3a6afa20/index.html).

# Introduction {#sec-introduction}

Early Arabic periodicals from the late nineteenth and early twentieth centuries,  such as Butrus al-Bustānī's *al-Jinān* (Beirut, 1876–86), Yaʿqūb Ṣarrūf, Fāris Nimr, and Shāhīn Makāriyūs' *al-Muqtaṭaf* (Beirut and Cairo, 1876–1952), Muhammad Kurd Ali's *al-Muqtabas* (Cairo and Damascus, 1906–18/19) or Rashīd Riḍā's *al-Manār* (Cairo, 1898–1941) are at the core of formative discourses that still reverberate through the Arabic-speaking Middle East: the Arabic renaissance (*al-nahḍa*), Arab nationalism, and the Islamic reform movement. The better known and at the time widely popular journals---unlike their smaller rivals and more ephemeral newspaper copies---do not face the ultimate danger of their last copy being destroyed in the current onslaught from iconoclasts, institutional neglect, and wars raging through Syria, Libya, Yemen, and Iraq. Yet, copies are distributed throughout libraries and institutions worldwide. This makes it almost impossible to trace discourses across journals and with the demolition and closure of libraries in the Middle East, they are increasingly accessible to the affluent Western researcher only.  

Digitisation promises an "easy" solution to the problems of preservation and access. Instant access to tens if not hundreds of thousands of *digitised* periodical issues from the late Ottoman Empire evokes the gold rush in the American west and many people imagine a promised land of magical one-click solutions to answer any question they might have in an instant. 

<!-- potential questions to be computationally answered with big data -->
The public and many scholars expect to be able to put a computer to such diverse tasks as: Show me all instances of the word *waṭan* across the ideosphere of the early Arabic press between Morocco and Iraq from its beginnings until the World War I. Or: Show me the discursive field of authors and their texts and its changes over time. Unfortunately, the eager student of *digitised* periodicals will immediately find tools, data and skills lacking.

<!-- some comments / summary of the following paper -->

This paper presents the dual race to catch up with methodological and epistemological developments outside the realm of Middle East studies and with the global networks of authors and readers enmeshed in late Ottoman periodicals. It introduces the project [OpenArabicPE](https://openarabicpe.github.io) as a framework to unite transcriptions of currently two early twentieth-century periodicals, *al-Muqtabas* and *al-Ḥaqāʾiq*, from gray online platforms with digital facsimiles. After substantial modelling efforts, we are now able to generate and analyse bibliographic datasets as well as run first stylometric analysis on this corpus of some 130 periodical issues of more than 2.2 million words.

<!-- image of a pages -->
<!-- word cloud -->
![Figure: Word cloud of authors published in *al-Muqtabas*](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/word-cloud_muqtabas-authors-bylines.png)

<!-- map -->
![Figure: Locations in bylines in *al-Muqtabas*](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/maps/map_muqtabas-bylines-me.png)

# The promised land of *digitised* Arabic periodicals

<!-- problem: there is no big data. on the difference between *digitised* and *digital* -->
The first question we encounter in our attempt to track the network of authors and texts is to which extent can we submit *digitised* periodicals to computational analysis, or rather, what is the meaning of *digitised* and *access*? The answer is, of course, sobering and will put off but the most enthusiastic readers: from large corporate and institution-backed platforms[^1] to gray online libraries[^2] *digitised* commonly  means nothing more than the provision of digital facsimiles. Some platforms, such as [Hathitrust](http://catalog.hathitrust.org/) and [Cengage Gale](http://gale.cengage.co.uk/arabic.aspx), include search functions, but these are extremely limited. The former, Google-powered, platform is obviously dysfunctional for Arabic text, but since the latter does not make the text layer accessible to scrutiny we will never know the extent of false negatives (one can manually check for false positives by going through the search results). Beyond copyright, *access* is always restricted to viewing individual pages in web interfaces and limited by subscription fees and membership of specific academic institutions.[^3] To computationally answer the above questions, however, one would need unrestricted access to truly *digital* editions---that is, machine-readable editions of the full text with embedded structural and semantic information and in a standardised exchange format.

[^1]: Such as [Cengage Gale](http://gale.cengage.co.uk/arabic.aspx), [Hathitrust](http://catalog.hathitrust.org/), the [British Library's "Endangered Archives Programme" (EAP)](http://eap.bl.uk/), [MenaDoc](http://menadoc.bibliothek.uni-halle.de/), ["*Jarāyid*: Arabic newspaper archive of Ottoman and Mandatory Palestine"](http://web.nli.org.il/sites/nlis/en/jrayed), the [Moise A. Khayrallah Center for Lebanese Diaspora Studies](https://lebanesestudies.omeka.chass.ncsu.edu/collections/browse) or the [Institut du Monde Arabe](http://ima.bibalex.org/IMA/presentation/home/list.jsf)
[^2]: such as [*Arshīf al-majallāt al-adabiyya wa-l-thaqāfiyya al-ʿarabiyya*](http://archive.sakhrit.co) or [*al-Maktaba al-Shāmila*](http://www.shamela.ws/), [*Mishkāt*](http://almeshkat.net/), [*Ṣayyid al-Fawāʾid*](http://saaid.net/) or [*al-Waraq*](http://www.alwaraq.net/)
[^3]: It must be noted that the US-based HathiTrust does not provide public or open access to its collections even to material deemed in the public domain under extremely strict US copyright laws when users try to connect to the collection from outside the USA. Citing the absence of editors able to read many of the languages written in non-Latin scripts, HathiTrust tends to be extra cautious with the material of interest to us and restricts access by default to US-IPs. These restrictions can be lifted on a case-by-case basis, which requires at least an English email conversation and prevents access to the collection for many of the communities who produced these cultural artefacts; see <https://www.hathitrust.org/access_use> for the access policies.

<!-- If the "data" is lacking, can we use (bibliographic) metadata? -->
Any sort of meaningful computational analysis of the global connections between authors, texts, and periodicals as a venue for publication and review requires access to reliable  standardised bibliographic metadata as a bare minimum. Unfortunately, reliable metadata on the article level is practically non-existant and the situation is only marginally better on the issue level. Available metadata is not commonly provided in a standard-compliant and machine-actionable format. Even if we had perfectly reliable digital re-mediations of the bibliographic information found in the periodical issues themselves, the vast majority of articles would remain outside our analytical scopes, since publishers did not provide (meaningful) bylines---most articles in both journals and newspapers from Beirut, Cairo or Damascus did not credit their authors. One approach would be to subject all articles to stylometric analysis but this again presupposes truly *digital* editions.

<!-- identify the areas to catch up with -->

Note that a the full text of a periodical is necessary but not sufficient for many analytical queries and distant reading. It is certainly insufficient for close reading. The full text of a periodical would be nothing but a string of words. But periodicals unite different texts of various genres from multiple authors. They are commonly grouped into issues and volumes and longer ones were frequently serialised and scattered across issues. Some of these texts will be reprints from other periodicals or first printed publications of much older manuscripts. Some of the texts are responses, etc. In order to make sense of the full text of a periodical for both humans and machines it has to be modelled.

<!-- get the full text -->
Optical character recognition (OCR), the technology to convert an image into a text, has come a long way and even hand-written text recognition (HTR) is fairly successful at least for Latin script.[^9] Automatic recognition of Arabic script, however, is severely lacking behind for a variety of reasons beyond the scope of this paper.[^4] Despite promising developments with the application of machine-learning technologies to pattern recognition,[^7] automatic conversion of images of early Arabic periodicals is hampered by two factors: 1. all OCR technologies depend on a fairly large training set of "gold standard" transcriptions as ground truth; 2.  low-quality fonts, inks, and paper employed at the turn of the twentieth century will inevitably result in poor print quality. Consequently these texts can currently only be reliably digitised by human transcription.{>>add footnote<<} Funds for transcribing the tens to hundreds of thousands of pages of an average mundane periodical are simply not available, despite of their cultural significance and unlike for valuable manuscripts and high-brow literature.

[^4]: C.f. [@Margner_2012]. {--For recent promising approaches using machine-learning and neural networks see [@Romanov_2016].--}For examples of the state of Arabic OCR even for well-funded corporations and projects, try searching inside Arabic works on Google Books or HathiTrust. The ["Early Arabic Printed Books" (EAPB) project](http://gale.cengage.co.uk/arabic), currently under development by GALE in collaboration with the British Library, makes repeated claims of employing "newly developed optical character recognition software (OCR) for early Arabic printed script" (see this [factsheet](http://gale.cengage.co.uk/images/EAPB-Factsheet_English_WEB.pdf)). But since they share neither the text layer nor the software their claims cannot be verified. As a substantial number of the digitised books in EAPB are written in languages other than Arabic that employ Arabic script (such as Farsī, Urdu or Ottoman Turkish) and as some works resemble complex manuscripts with multiple commentaries around a main text fully automated text-retrieval is highly unlikely. 

[^7]: The [Open Islamicate Text Initiative (OpenITI)](http://iti-corpus.github.io/) project planned to publish its tool chain in 2018. For an overview of their work see <http://islamichistorycommons.org/mem/wp-content/uploads/sites/55/2017/11/UW-25-Savant-et-al.pdf>.

[^9]: One major research project for HTR is [transkribus.eu](https://transkribus.eu/Transkribus/).

Gray online-libraries of Arabic literature, namely [*al-Maktaba al-Shamila* (*shamela.ws*)][shamela], [*Mishkat*][almeshkat], [*Saydal-Fawa'id*][saaid] or [*al-Waraq*][alwaraq], provide access to a vast body of (mostly classical) Arabic texts including transcriptions of unknown provenance, editorial principals, and quality for some of the mentioned periodicals. These gray "editions" lack information linking the digital representation to material originals, namely bibliographic metadata and page breaks, which makes them almost impossible to employ for scholarly research.

Since we do not have the resources to proof and correct these texts, we had the idea to unite transcriptions from gray online libraries with the digital facsimiles from other sources as a means to verify the quality of the digital text. Thus "Open Arabic Periodical Editions" (OpenArabicPE) was born in autumn 2015. 

# OpenArabicPE attempts at catching up

<!-- this needs to be expanded upon -->

[OpenArabicPE](https://github.com/openarabicpe) establishes a framework for open, collaborative, and fully-referencable scholarly digital editions of early Arabic periodicals. The guiding principles of OpenArabicPE can be summarised as *accessibilty*, *sustainability*, *credibility*. Starting with the mostly Damascene periodicals *al-Muqtabas* and *al-Ḥaqāʾiq*, OpenArabicPE demonstrates that one can produce scholarly editions that offer solutions for most of the above-mentioned problems---including the absence of expensive infrastructure---through re-purposing well-established open software platforms and by combining the virtues of immensely popular, but non-academic (and, at least under US copyright laws, occasionally illegal) online libraries of volunteers on the one hand with academic scanning efforts as well as editorial expertise on the other. 

![Figure: Project scheme](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/OpenArabicPE-organigramme_horizontal.png)

Within OpenArabicPE we devise workflows and tools to transform digital texts from [*shamela.ws*][shamela] into an open, standardised file format (XML) following the [Text Encoding Initiative (TEI)](https://www.tei-c.org)'s guidelines,[^8] to generate bibliographic metadata, and to render a parallel display of text and facsimile in a web browser. We add light structural mark-up for articles, sections, authors, and bibliographic metadata, and link each page to facsimiles from various sources, namely [EAP][bl], [HathiTrust][hathitrust], and [archive.sakhrit.co][]. The latter step, in the process of which we also make first corrections to the transcription, though trivial, is the most labour-intensive because page breaks were {--commonly--} ignored by *shamela.ws*'s anonymous transcribers.[^6] This point needs to be emphasised: every one of the c.8500 pages breaks needs to manually marked by volunteers in order to link facsimiles to the digital text and thus make the text verifiable for human readers. So far Dimitar Dragnev, Talha Güzel, Xaver Kretzschmar, Daniel Lloyd, Klara Mayer, Manzi Tanna-Händel and Layla Youssef have contributed their time to this task.

[^6]: In other instances, such as the [two volumes of Yūsuf Ilyān Sarkīs' *Muʿjam al-maṭbūʿat al-ʿarabiyya wa-l-muʿarraba* (Miṣr: Maṭbaʿat Sarkīs, 1928)](http://shamela.ws/index.php/book/1242), *shamela.ws* did provide page breaks that correspond to a printed edition.
[^8]: TEI XML is the quasi-standard of textual editing and required by funding bodies and repositories for long-term archiving. 

![Figure: Web view of [al-Muqtabas 6/2](https://rawgit.com/tillgrallert/digital-muqtabas/master/xml/oclc_4770057679-i_61.TEIP5.xml)](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/boilerplate_muqtabas.png)

The editions (TEI, markdown, and a web-display) are hosted as a GitHub repository with open licenses for reading, contribution, and re-use.[^10] {>>mention collaboration with Leipzig and the integration of Muqtabas into CLARIN<<} As part of the editions we also provide structured bibliographic metadata for every article  in machine-readable format that can easily be integrated into larger bibliographic information systems or individual scholars' reference managing software. In order to improve access to individual articles and allow for a search of bibliographic metadata we feed this data into a [public Zotero group](https://www.zotero.org/groups/openarabicpe).

[^10]: We claim that text of *al-Muqtabas* and *al-Ḥaqāʾiq* itself is in the public domain even under the most restrictive definitions (i.e. in the USA). {>>Further note on licences: MIT and Creative Commons [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/) <<} the anonymous original transcribers at *shamela.ws* do not claim copyright; and we only link to publicly accessible facsimile's without copying or downloading them.

With OpenArabicPE we argue that by linking facsimiles to the digital text, every reader can validate the quality of the transcription against the original. We thus remove the greatest limitation of crowd-sourced or gray transcriptions and the main source of disciplinary contempt among historians and scholars of the Middle East. Improvements of the transcription and mark-up can be crowd-sourced with clear attribution of authorship and version control using .git and GitHub's core functionality. Such an approach as proposed by Christian Wittern {2013} has recently seen a number of concurrent practical implementations such as project [GITenberg](https://gitenberg.github.io/) led by Seth Woodworth, Jonathan Reeve's [Git-lit](https://github.com/Git-Lit/git-lit), and others.

For the future we plan to produce the necessary ground truth to train OCR technologies from some hundred pages of either journal.

{>>Some paragraphs on the importance of the two journals<<}


<!-- corpus -->
<!-- full editions -->
<!-- some information on al-Muqtabas -->

<!-- some information on al-Ḥaqāʾiq -->



<!-- bibliographic metadata -->

# Network of authors and texts

With major work on modelling both *al-Muqtabas* and *al-Ḥaqāʾiq* done, we can now begin to submit this corpus to initial analyses of the networks of authors and their texts as well as the material read and reviewed in Damascus.

## OpenArabicPE's corpus

The corpus comprises TEI files for each issue of *al-Muqtabas* and *al-Ḥaqāʾiq* The edition of *al-Muqtabas* gathers all 96 issues published between 1906 and 1917/18 with a total of some 7.000 pages and almost 2 million words. {>>comment on publication dates<<} Issues consist of longer independent articles and sections with shorter articles such as brief reports on new discoveries and book announcements. Issues and pages differed widely in length. On average, each issue contained 65 pages with almost 300 words or 20354 word per issue.

![Figure: Words per page and page counts for *al-Muqtabas*](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/rplot_muqtabas-counts_words-pages-bars.png)

<!-- statistics on our editions -->
The edition of *al-Ḥaqāʾiq* comprises all 36 issues, grouped into three volumes and published by ʿAbd al-Qādir al-Iskandarānī in Damascus between 1910 and 1913. {>>comment on publication dates<<} Pages contain much less text and issues are much shorter than *al-Muqtabas* with a total of 300186 words across 1436 pages (as some 17 pages are missing from the transcription, the word count is too low). Save for a double issue, the vast majority of issues (28 of 36) comprised 40 pages with an average of slightly more than 200 words each. This results in an average 8577 words per issue compared to the 20354 words of *al-Muqtabas*.

![Figure: Words per page and page counts for *al-Ḥaqāʾiq*](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/rplot_haqaiq-counts_words-pages-bars.png)

<!-- state of the data -->
The quality and significance of the analysis is directly dependent on the quality of the information provided by the periodicals themselves and of our mark-up in the TEI source files. All relevant personal and place names in bylines and other source information must be marked up and linked to local and external authority files. References to authority files allow for the necessary disambiguation and grouping of entities that might be referenced by multiple names in our periodicals, such as "Rashīd Riḍā" and "Owner of al-Manār". In addition, by linking references to external authority files and the semantic web, we can harvest additional information on authors and locations, namely the geolocation for toponyms, transcriptions into Latin script necessary for working with most visualisation tools, and life dates for persons in order to establish the age of authors upon publication.{>>Comment on the issue of many visualisation tools, such as R and Gephi for macOS, not working with Arabic script<<}

## analysis of metadata

Before looking at this aggregated information is is worth going back to the bibliographic metadata, its shortcomings and the resulting consequences for our analysis. *al-Muqtabas* printed a total of 2737 articles, 2020 of which were shorter articles in sections. Of the 717 independent articles, about two fifths (284) explicitly mentioned an author. Another 39 shorter articles carry bylines. The situation is similar at *al-Ḥaqāʾiq*: Only one fifth (76) of the 360 articles provide explicit author information. {>>add information on the number of words, which is more meaningful than the number of articles<<} We can currently identify only a maximum of 128 named authors for *al-Muqtabas* and less than 60 for *al-Haqāʾiq* [See word clouds below].[^5] Quite a significant number appear only with their initials, particularly in *al-Ḥaqāʾiq* and all of them were men. Only 50 authors published more than one article in *al-Muqtabas*. Two of the four most prolific authors with more than ten bylines to their names wrote from Baghdad (See table below): Maʿrūf al-Ruṣāfī (24 articles) and Buṭrus bin Jibrāʾīl Yūsuf ʿAwwād, using the pen name Sātsunā (14). ʿĪsā Iskandar al-Maʿlūf (20) wrote mostly from Zaḥle and Yūsuf Jirjis Zakham (13) from Omaha and Lincoln, Nebraska, USA. Only the fifth most prolific author was a native resident of Damascus: Jamāl al-Dīn al-Qāsimī (8). {>>add comments on genre of texts by these authors<<}

{>>al-Ḥaqāʾiq<<}
<!-- The majority of the remaining authors contributed from the cities of Greater Syria and Egypt, but some wrote from cities in France. -->

[^5]: These word clouds were produced with R on macOS. Take note that most visualisations in R for macOS---unlike Windows or Linux---cannot correctly display Arabic script.

<!-- Muqtabas: authors by byline -->

| rank |            name           | words | articles |
|------|---------------------------|-------|----------|
|    1 | Maʿrūf al-Ruṣāfī          | 12437 |       24 |
|    2 | ʿĪsā Iskandar al-Maʿlūf   | 23297 |       20 |
|    3 | Sātsunā                   | 19849 |       14 |
|    4 | Yūsuf Jirjis Zakham       | 21613 |       13 |
|    5 | Jamāl al-Dīn al-Qāsimī    | 38541 |        8 |
|    6 | Muḥammad Kurd ʿAlī        | 42489 |        7 |
|    7 | Aḥmad Zakī                | 40311 |        7 |
|    8 | Muḥammad Riḍā al-Shabībī  | 17894 |        7 |
|    9 | ʿAbd al-Qādir al-Maghribī | 14074 |        7 |
|   10 | Rafīq al-ʿAẓm             | 13237 |        7 |
|   11 | Aḥmad Taymūr              |  7905 |        7 |

<!-- plots -->
![Figure: Word cloud of authors published in *al-Muqtabas*; by number of articles](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/word-cloud_muqtabas-authors-bylines.png)

![Figure: Word cloud of authors published in *al-Ḥaqāʾiq*](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/word-cloud_haqaiq-authors-bylines.png)

## going beyond bibliographic metadata

We can easily add another dimension to our analysis of the authors published in *al-Muqtabas* and *al-Ḥaqāʾiq*. One could argue that, within genre boundaries, the number of texts is less significant for the relative importance of an author than the total length of all texts by a single author. With access to the full text with structural mark-up, we can easily calculate word counts.{-- The picture changes decisively if we consider total word counts instead of bylines/articles.--} Muḥammad Kurd ʿAlī himself would immediately become the most important author (see table below) due to his lengthy reports from a journey across Europe, which he later published as a collection titled *Gharāʾib al-gharb*. He would be followed by Aḥmad Zakī (Pasha), an important Egyptian philologist and politician, and by Jamāl al-Dīn al-Qāsimī. Also included in this list of the ten most prolific authors published in *al-Muqtabas*, is Ibn al-Muqaffaʿ (d.759), the famous author of *Kalīla wa dhimna*, which points to an important function of *al-Muqtabas*: the publication of hitherto unpublished manuscripts and the re-print of classics. This is also attested to by the presence of Aḥmad (Bey) Taymūr in the above list of most important authors by number of articles. An avid collector of manuscripts, Aḥmad Taymūr provided many such manuscript to Muḥammad Kurd ʿAlī for publication and he frequently wrote the introductions.

<!-- Muqtabas: authors by word count -->

| rank |            name           | words | articles |
|------|---------------------------|-------|----------|
| 1    | Muḥammad Kurd ʿAlī        | 42489 |        7 |
| 2    | Aḥmad Zakī                | 40311 |        7 |
| 3    | Jamāl al-Dīn al-Qāsimī    | 38541 |        8 |
| 4    | Jirjī Ḥaddād              | 24124 |        5 |
| 5    | ʿĪsā Iskandar al-Maʿlūf   | 23297 |       20 |
| 6    | Yūsuf Jirjis Zakham       | 21613 |       13 |
| 7    | Sātsunā                   | 19849 |       14 |
| 8    | Muḥammad Riḍā al-Shabībī  | 17894 |        7 |
| 9    | Ibn al-Muqaffaʿ [sic!]    | 15520 |        4 |
| 10   | ʿAbd al-Qādir al-Maghribī | 14074 |        7 |
| ...  |                           |       |          |
| 14   | Maʿrūf al-Ruṣāfī          | 12437 |       24 |

![Figure: Word cloud of authors published in *al-Muqtabas*; by number of words](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/word-cloud_muqtabas-authors-words.png)

*al-Muqtabas* and *al-Ḥaqāʾiq*, like any other periodical at the time, seriously violated the Ottoman press code that required identifiable author information being published alongside each article. This also means that any analysis of bibliographic information is based on only a small sample of either periodical. 

What are the consequences of such a severe lack of information and are there means of filling the gap? The obvious approach to follow would be to submit the full text of every article to stylometric analysis, which is a statistical approach to compute stylistic similarities and dissimilarities between texts. This is not the space to discuss the intricacies of stylometry for authorship attribution, the available tools and the necessary amount of pre-processing to be applied to Arabic texts before submitting them to stylometric analysis. The important catch here is that in order to establish similarities, one has to have access to a significant corpus of digital texts by authors likely to be found among the unattributed texts. If we only compare every article in our periodical corpus to every other article in the same corpus, we cannot possibly identify any author not yet named in a byline. Instead, the best we could hope for would be to establish groups of texts that have a certain likelihood of having been authored by the same person.

Successful stylometric authorship attribution, will not fill the gap in geographic information in all but the most obvious and likely case, namely that a large part of the unattributed articles were indeed written by a periodical's editor. In the case of *al-Muqtabas*, we know the whereabouts of Muḥammad Kurd ʿAlī during most of the time he published the journal and could thus easily assign locations to articles. However, given that we are interested in the *network* of authors, texts, and locations, this would be an utterly pointless endeavour.


If we assume that information on the place of writing of any one article was not generally considered sensitive information to be protected in all but the most harmless cases and that most articles where authored by the publishers and at the place of publication, one can nevertheless arrive at a meaningful picture of the geographic distribution of authors and the origin of articles:

![Figure: Locations in bylines in *al-Muqtabas*](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/maps/map_muqtabas-bylines-me.png)

![Figure: Locations in bylines in *al-Ḥaqāʾiq*](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/maps/map_haqaiq-bylines-all.png)


{>>missing comment on maps<<}

{>>missing conclusion<<}

[almeshkat]: http://almeshkat.net/
[alwaraq]: http://www.alwaraq.net/
[bibalex]: http://ima.bibalex.org/IMA/presentation/home/list.jsf
[menadoc]: http://menadoc.bibliothek.uni-halle.de/
[bl]: http://eap.bl.uk/
[hathitrust]: http://catalog.hathitrust.org/
[openarabicpe_schema]: https://github.com/OpenArabicPE/OpenArabicPE_ODD
[rawgit]: https://rawgit.com/tillgrallert/digital-muqtabas/master/xml/oclc_4770057679-i_54.TEIP5.xml#pb_61.d1e2036
[rawgit 2]: https://rawgit.com/tillgrallert/digital-muqtabas/master/xml/oclc_4770057679-i_59.TEIP5.xml#pb_51.d1e2281
[rawgit 3]: https://rawgit.com/tillgrallert/digital-muqtabas/master/xml/oclc_4770057679-i_38.TEIP5.xml#p_60.d1e2238
[rawgit 4]: https://rawgit.com/tillgrallert/digital-muqtabas/master/xml/oclc_4770057679-i_39.TEIP5.xml#gap_1.d1e3111
[rawgit 5]: https://rawgit.com/tillgrallert/digital-muqtabas/master/xml/oclc_4770057679-i_71.TEIP5.xml#pb_126.d1e4373
[saaid]: http://saaid.net/
[shamela]: http://www.shamela.ws/
[shamela 2]: http://shamela.ws/index.php/book/26523
[wikisource]: https://ar.wikisource.org/wiki/%D9%85%D8%AC%D9%84%D8%A9_%D8%A7%D9%84%D9%85%D9%82%D8%AA%D8%A8%D8%B3/%D8%A7%D9%84%D8%B9%D8%AF%D8%AF_1
