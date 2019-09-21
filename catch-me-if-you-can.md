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
tags:
    - periodical studies
    - social network analysis
    - stylometry
    - Arabic periodicals
    - digital humanities
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

>This paper originated in a presentation at Turkologentag 2018 in Bamberg, Germany, 19--21. September 2018.

>The current stable draft of this paper is version [v0.1](https://rawgit.com/tillgrallert/p3a6afa20/v0.1/index.html) and contains unprocessed references to sources and secondary literature, cross-references, and CriticMarkup. To comment / review / annotate this version via hypothes.is click [here](https://via.hypothes.is/https://rawgit.com/tillgrallert/p3a6afa20/v0.1/index.html). The most recent changes are available [here](https://tillgrallert.github.io/p3a6afa20/index.html).

# Introduction

{>>research questions are still missing<<}

This paper presents the dual race to catch up with methodological and epistemological developments outside the realm of Middle East studies and with the global networks of authors and readers enmeshed in late Ottoman periodicals. 

{>>add comment on the need to build one's own corpus for working on texts in non-Western languages<<}

It introduces the project [OpenArabicPE](https://openarabicpe.github.io) as a framework to unite transcriptions of {~~currently two~>a small number of~~} early twentieth-century periodicals{--, *al-Muqtabas* and *al-Ḥaqāʾiq*,--}{>>the corpus needs to be discussed at a later stage<<} from grey online platforms with digital facsimiles for the purpose of validating the former. After substantial modelling efforts, we are now able to generate and analyse bibliographic datasets as well as run first stylometric analyses on this corpus of some {==130 periodical issues of more than 2.2 million words==}{>>update with latest numbers<<}. This corpus is small if compared to the vast data sets available for the global north through [*Chronicling America*](https://chroniclingamerica.loc.gov/), [*Trove*](https://trove.nla.gov.au/) Australia, the [*British Newspaper Archive*](https://www.britishnewspaperarchive.co.uk/) etc. {>>add projects<<}, which gave rise to numerous distant reading projects.[^16] Although our approach can by no means be characterised as distant reading of big data, it is the first systematic attempt to empirically answer core questions for the nascent field of Arabic periodical studies,{--[^17]--} which are in turn indispensable for a proper source critique if one wanted to employ these periodicals for the historiography of the late Ottoman Eastern Mediterranean. For the purpose of the present paper, we will focus our exploration on the question of authorship and references to other periodical titles and the resulting intellectual, social and geographic networks.

[^16]: For studies assessing these corpora and the methodological implications see {Nicholson 2013;Brake 2012;Horrocks 2014;Mussell 2012;Gooding 2016}.For studies and projects based on *Chronicling America* see, for example, {Cordell 2017;Lorang 2015;Torget 2011;Cordell 2015;Smith 2015;Smith 2013;Cordell 2013;Torget 2012;Torget 2012a}. For a study based on *Trove* see {Bode 2016}.

{--[^17]: There are only very limited systematic studies on Arabic periodicals, everyone of which is concerned with a single periodical only; c.f. {Glaß 2004b;Cioeta 1979a}. At the time of writing, only one study made use of digital texts: {Zemmin 2018}; for methodological comments see also {Zemmin 2016@232-233}.--}

The periodical press of the late Ottoman Eastern Mediterranean has received scholarly attention since the early twentieth century. Early Arabic periodicals from the late nineteenth and early twentieth centuries, such as Butrus al-Bustānī's *al-Jinān* (Beirut, 1876–86), Yaʿqūb Ṣarrūf, Fāris Nimr, and Shāhīn Makāriyūs' *al-Muqtaṭaf* (Beirut and Cairo, 1876–1952), Muhammad Kurd Ali's *al-Muqtabas* (Cairo and Damascus, 1906–18/19) or Rashīd Riḍā's *al-Manār* (Cairo, 1898–1941) are at the core of formative discourses that still reverberate through the Arabic-speaking Middle East: the Arabic (cultural) renaissance (*al-nahḍa*), Arab nationalism, and the Islamic reform movement.
However, scholarly approaches to these periodicals have been, for a long time, both encyclopaedic and anecdotal. Often compiled by authors who themselves were journalists, these works adhere to a specific political view of Arab nationalism.[^28] After the publication of some union catalogues and indexes,[^29] focus shifted to the intellectual history of the *naḥda* and Arab nationalism from the 1970s onwards. The focus of this work was---and to a large extent still is---on opinion pieces and editorials in a small sample of canonical journals while the {--social, economic and intellectual --}historiography of the periodical press itself was relegated to the margins. Two noteworthy exceptions to this rule are Donald Cioeta's work on the history of *Thamarāt al-Funūn* and censorship in Ottoman Beirut[^30] and Ami Ayalon's extensive writings on the press in the Arab Middle East.[^31] Detailed studies on longer---if not entire---periods of individual publications are still lacking beyond Cioeta's unpublished thesis and Dagmar Glaß' study on *al-Muqtaṭaf*.[^32]



{>> add one sentence on core questions of authorship, readership, modes of production etc. being open. add comment on the geographic bias of Cairo and Beiurt and nothing beyond<<} 
{>>problem of access and basic information on holdings<<}

[^28]: E.g. {Jundī 1925; Shaykhū 1926; Sarkīs 1929}, {Muruwwa 1961; AlRifāʿī 1969; AlRifāʿī 1969a; Dāghir 1950; Dāghir 1978; Ilyās 1982; Khūrīya 1976}
[^29]: E.g. {ElHadi 1965; AhmedBioud 1969; Hopwood 1970; Murād 1977; Auchterlonie 1977; Aman 1979; DeJong 1979; Duman 1982a; Duman 1986}
[^30]: {Cioeta 1979; Cioeta 1979a}.{-- Due to a fatal accident soon after completing his thesis, he published only one further article: {Cioeta 1982}.--}
[^31]: {Ayalon 1995}; {Ayalon 1984; Ayalon 1985; Ayalon 1987a; Ayalon 1987; Ayalon 1992; Ayalon 2002; Ayalon 2008}.
[^32]: {Glaß 2004b} {>>Add comment on {Dierauff 2018}{Beška 2017}<<}

The better known and at the time widely popular journals---unlike their smaller rivals and more ephemeral newspaper copies---do not face the ultimate danger of their last copy being destroyed in the current onslaught from iconoclasts, institutional neglect, and wars raging through Syria, Libya, Yemen, and Iraq. Yet, copies are scattered across libraries and institutions worldwide. This makes it almost impossible to trace discourses across journals and with the demolition and closure of libraries in the Middle East, they are increasingly accessible to the affluent Western researcher only.

A quick look at *al-Muqtabas*{--, one of the journals in the corpus at the basis of this paper--} shall {--suffice to--} illustrate this point. A search in [WorldCat](https://www.worldcat.org) for the nine volumes of *al-Muqtabas* {--using a combination of Arabic and transcriptions into Latin script--} will return six different bibliographic entries, the first of which has 13 variants (called "editions" in the context of WorldCat), pointing to 34 libraries. If one follows each entry to the holding library's catalogue, one will find that the large majority of collections is incomplete and that collections commonly combine original volumes, reprints, microfilms, microfiches and even photo copies. {>>comment on the geographic distribution of collections<<}

![Figure: geographic distribution of library holdings of *al-Muqtabas*](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/visualization/maps/map-oclc_4770057679-holdings-vol_1-9.png)

Digitisation promises an "easy" solution to the problems of preservation and access. Instant access to tens if not hundreds of thousands of *digitised* periodical issues from the late Ottoman Empire evokes the gold rush in the American west and many people imagine a promised land of magical one-click solutions to answer any question they might have in an instant.
The public and many scholars expect to be able to put a computer to such diverse tasks as a keyword search: Show me all instances of the word *waṭan* (Arabic for "homeland", "nation") across the ideosphere of the early Arabic press between Morocco and Iraq from its beginnings until the World War I. Or a social network analysis: Show me the discursive field of authors and their texts and its changes over time. These are important and---for a variety of reasons, some of which will be discussed in this article---still open questions. Unfortunately, the eager student of *digitised* Arabic periodicals will immediately find tools, data and skills lacking.

# The promised land of *digitised* Arabic periodicals

<!-- problem: there is no big data. on the difference between *digitised* and *digital* -->

The first question we encounter in our attempt to track the network of authors and texts is to which extent can we submit *digitised* periodicals to computational analysis, or rather, what is the meaning of *digitised* and *access*? The answer is, of course, very different from periodical corpora in Western languages. It is sobering and will put off but the most enthusiastic readers: from large corporate and institution-backed platforms[^1] to grey online libraries[^2] *digitised* commonly  means nothing more than the provision of digital facsimiles in the context of Arabic and Ottoman periodicals. Some platforms, such as [Hathitrust](http://catalog.hathitrust.org/) and [Cengage Gale](http://gale.cengage.co.uk/arabic.aspx), include search functions, but these are extremely limited. The former, Google-powered, platform is obviously dysfunctional for Arabic text if one has a look at the text layer. The latter makes grand claims of "Newly-developed optical character recognition software (OCR) for early Arabic printed script"[^18] but does not make the text layer accessible to scrutiny. We will therefore never know the extent of false negatives (one can manually check for false positives by going through the search results). Beyond copyright, *access* to these *digitised facsimiles* is always restricted to viewing individual pages in web interfaces and limited by subscription fees and membership of specific academic institutions.[^3] To computationally answer the above questions, however, one would need unrestricted access to truly *digital* editions---that is, machine-readable editions of the full text with embedded structural and semantic information and in a standardised exchange format.[^19]

[^1]: Such as [Cengage Gale](http://gale.cengage.co.uk/arabic.aspx), [Hathitrust](http://catalog.hathitrust.org/), the [British Library's "Endangered Archives Programme" (EAP)](http://eap.bl.uk/), [MenaDoc](http://menadoc.bibliothek.uni-halle.de/), ["*Jarāyid*: Arabic newspaper archive of Ottoman and Mandatory Palestine"](http://web.nli.org.il/sites/nlis/en/jrayed), the [Moise A. Khayrallah Center for Lebanese Diaspora Studies](https://lebanesestudies.omeka.chass.ncsu.edu/collections/browse) or the [Institut du Monde Arabe](http://ima.bibalex.org/IMA/presentation/home/list.jsf)
[^2]: such as [*Arshīf al-majallāt al-adabiyya wa-l-thaqāfiyya al-ʿarabiyya*](http://archive.sakhrit.co) or [*al-Maktaba al-Shāmila*](http://www.shamela.ws/), [*Mishkāt*](http://almeshkat.net/), [*Ṣayyid al-Fawāʾid*](http://saaid.net/) or [*al-Waraq*](http://www.alwaraq.net/)
[^3]: It must be noted that the US-based HathiTrust does not provide public or open access to its collections even to material deemed in the public domain under extremely strict US copyright laws when users try to connect to the collection from outside the USA. Citing the absence of editors able to read many of the languages written in non-Latin scripts, HathiTrust tends to be extra cautious with the material of interest to us and restricts access by default to US-IPs. These restrictions can be lifted on a case-by-case basis, which requires at least an English email conversation and prevents access to the collection for many of the communities who produced these cultural artefacts; see [https://www.hathitrust.org/access_use](https://www.hathitrust.org/access_use) for the access policies.
[^18]: {website_eapb}
[^19]: For good overviews on the issue of digital (scholarly) editions see {Driscoll 2016;Pierazzo 2015;Sahle 2013}.

<!-- If the "data" is lacking, can we use (bibliographic) metadata? -->

In the absence of *digital* editions, any meaningful computational analysis of the {--global--} connections between authors, texts, and periodicals as a venue for publication and review requires access to reliable standardised bibliographic metadata as a bare minimum. Unfortunately, even this data is practically non-existent{-- on the article level and the situation is only marginally better on the issue level--}. This is due to ambiguity and incorrect data found in the original artefact; to lacking familiarity with the particularities of these artefacts among cataloguers, librarians and scholars; and to a software stack ill-suited for anything but Western concepts of dates and names and Western scripts. 

{>>Add comment on faulty publication data as provided by the periodicals themselves; a) dates, b) names<<}
Periodicals seem to provide no dating challenges since publication dates were conveniently recorded in a masthead. However, periodicals across the Arabic speaking late Ottoman Eastern Mediterranean made use of at least four calendars. Newspapers and journals provided dates in any combination of the Ottoman fiscal, or *mālī* calendar and the reformed Julian calendar as well as the better known Islamic *hijri* and Gregorian calendars. In addition to at least three different year counts, these calendars and their users also differed in their conception of the calendric day. Most retained the old notion of a day commencing at sundown, while others adopted *alla franca* time with 24 equinoctial hours and a date change at midnight.[^19] Unfortunately supplied dates from mastheads frequently neither matched each other nor the day of the week the paper was supposedly printed on. A particularly illuminating example in our corpus can be found in the masthead to issue 6 of the Damascene journal *al-Ḥaqāʾiq* that read "First of the holy month of *Muḥarram* 1229 [*hijrī*], 3 *Kānūn Awwal* 1327 [*mālī*], and 20 December (*Kānūn Awwal*) of the year 1911 [Gregorian]".[^23] This line contains at least four errors: First the *hijrī* date is set in the wrong century and should read 1329. Second, the days of the *mālī* and Gregorian dates got mixed up. The Gregorian calendar was thirteen days ahead of Julian calendars since the year 1900. The corrected *mālī* date should read 20 *Kānūn Awwal* instead of the third, but because the *mālī* years began in spring with the month of *mārt* (March), the year count should not have been incremented to 1327 with the beginning of the new *hijrī* year. Therefore the correct *mālī* date would have been "20 *Kānūn Awwal* 1326".  The Gregorian date, finally, is even wrong after fixing the mix-up of days with the *mālī* date. Instead of *Kānūn Awwal* (December) it should be *Kānūn Thānī* (January) and since December has 31 days, the correct Gregorian date should ultimately read "2 (instead of the substituted 3 from the original, faulty, *mālī* date) January 1911". How should one record this bibliographic nightmare? And which date-calendar combination should be considered the authoritative one? What if recorded publication dates were fictional to simulate a regular publication cycle and should therefore be conceived of as issue numbers that have only limited relation to an actual date?[^24] 

[^23]: *al-Haqāʾiq* 1(6), available online at <https://openarabicpe.github.io/digital-haqaiq/xml/oclc_644997575-i_6.TEIP5.xml>. Note that digital facsimiles are geo-fenced and only accessible to US IPs.
[^24]: *al-Muqtabas*, for instance, was severely lagging behind its publication schedule by summer 1909. [No. 4(7)](https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_42.TEIP5.xml) was scheduled for Rajab 1327 aH (July/August 1909) according to its masthead but only published in the first week of April the following year; see {muqtabas 76-eap@3}. *al-Ḥaqāʾiq* is more difficult to date through external source because unlike *al-Muqtabas* it was only rarely mentioned in other publications. However, a prolonged dispute with the newspaper *al-Muqtabas* in 1911 provides some clues. {haqaiq i:12@476} referenced {muqtabas 288-eap}. Therefore, it must have been published at least 10 days after the publication date provided by the masthead. {>>*al-Ḥaqāʾiq* 1(6) referenced an article in *al-Muqtabas* 1 December 1910 (#539)<<}

{>>2) lack of knowledge among cataloguers<<}
Any attempt to answer these questions relies on the affordances of available information systems, that is people and their skills, abstract concepts, and actual tools to record and retrieve these data points.
But cataloguers, librarians and even specialists of the late Ottoman Eastern Mediterranean are frequently unfamiliar with calendric systems beyond the solar Gregorian and the Islamic lunar *hijrī* calendars. *Mālī* years are frequently misread as *hijrī* years, which introduces a margin of error of up to two years for the last decades before World War I.[^25]
{>>3) short-comings of the software<<}
Second, most software is unable to work with anything but Gregorian dates out of the box.  Even if cataloguers were able to correctly establish the calendar used in a periodical's masthead, the computing infrastructure would not allow them to enter this date into the digital record.[^20]
Finally, even if bibliographic data is internally kept in structured {--and machine-actionable--} form, it is not commonly shared in a standard-compliant and machine-actionable format, such as MARC or MODS.[^21] A good example for this state of affairs is the British Library's otherwise excellent Endangered Archives Programme (EAP), which digitised periodical holdings of the al-Aqsa Mosque's library in Jerusalem. If we look at the [fourth volume](https://eap.bl.uk/archive-file/EAP119-1-4-3) of the journal *al-Muqtabas* available through EAP, we find that bibliographic information is solely provided in unstructured plain text either through the web interface or the IIIF API.[^22] {~~In addition, p~>P~~}ublication dates are provided as Gregorian months even though the cover clearly states that *al-Muqtabas* follows the "Arabic", i.e. Islamic *hijrī*, calendar and despite each issue reporting the publication date as *hijrī* month. Consequently, there is a dissonance between the facsimile and the bibliographic information. *al-Muqtabas* 4(1) recorded the month of *Muḥarram* 1327 aH in its masthead. Depending on the local observation of the moon in Damascus, the journal's place of publication, this month began around 27 January 1909. Should *al-Muqtabas* 4(1) therefore be considered the January issue? The cataloguers at EAP clearly thought so or their cataloguing software did not allow for date ranges.

[^25]: Stefan Weber and Jens Hanssen, for instance, missed the fact that the birthday of Sultan ʿAbdülḥamīd II (1876--1909) was celebrated according to the Islamic *hijrī* calendar and thus rotated through the solar year. The annual celebrations of the anniversary of the ʿAbdülḥamīd II's accession to the throne were celebrated according to the empire's *mālī* calendar. Yet, leading scholars read these dates as pertaining to the *hijrī* calendar. Due to the mix-up in 1872 and the resulting growing difference between the two calendars, the ʿAbdülḥamīd II's silver jubilee on the throne is wrongly dated to 1901 instead of 1900. {Hanssen 2005@238, 243ff.; Weber 2009@418-420;Deringil 1998@29; Uluengin 2010@20}.

[^19]: The Islamic *hijrī* calendar is a lunar calendar beginning the year with 1 *Muḥarram* and counting years since the prophet Muḥammad's flight (*hijra*) from Mecca to Medina in 622. Dates differ between locations as the beginning of the month is based on sightings of the new moon. They cannot, therefore, be reliably computed. A common workaround without recourse to empirical observations as provided in large tabular publications is to compute the astronomic lunar calendar instead. The reformed Julian calendar is a solar calendar beginning the year with 1 January. Every one hundred years the difference between the Gregorian and Julian calendar increases by one day due to different rules for adding an intercalated 366th day every four years. In the Ottoman context, the reformed Julian calendar is commonly referred to as *rūmī*. Arabic periodicals usually labelled this calendar as *sharqī* (Eastern). The Ottoman fiscal *mālī* calendar is a lunosolar calendar. It is based on the Old Julian calendar beginning the year with 1 March and was designed to synchronise the year count with the *hijrī* calendar. Introduced in 1676 it is also sometimes confusingly called *rūmī*. {--Every 33 lunar years, a *hijrī* year would complete within a single solar *mālī* year. In this case the counting of the *mālī* years skipped a year to catch up with the faster *hijrī* calendar.--} Due to a printing error in the coupon booklets for the Ottoman consolidated debt repayment program for 1872{-- (1288 M instead of 1289 M)--}, synchronisation of *mālī* and *hijrī* years was henceforth abolished. {>>some references needed<<} {Jajko 1993;Rose 1991;Deny 1921;Georgeon 2011}.

[^20]: Consider, for instance, the quasi standard for digital scholarly editions, TEI, which is expressed in XML. According to the XPath specifications, the [`format-date()`](https://www.w3.org/TR/xpath-functions-30/#func-format-date) function supports a number calendars beyond the Gregorian standard, including the Islamic *hijrī* calendar, since version 2.0. However, the actual support for calendars and languages is implementation-dependent and Saxon, the main XSLT, XPath and XQuery processor, has not implemented any of these alternative calendars; see [documentation for `format-dateTime()`](https://www.saxonica.com/html/documentation/functions/fn/format-dateTime.html).

[^21]: The [MAchine-Readable Cataloging (MARC)](http://www.loc.gov/marc/) is a data format maintained by the [Network Development and MARC Standards Office of the Library of Congress (NDMSO)](http://www.loc.gov/marc/ndmso.html). MARC can be serialised as XML but frequently isn't. The [Metadata Object Description Schema (MODS) standard](http://www.loc.gov/standards/mods/), in contrast, is expressed in XML and more human-readable. It is also maintained by the Network Development and MARC Standards Office with input from users.

[^22]: {>>Footnote on IIIF<<}

Even if we had perfectly reliable digital re-mediations of the bibliographic information found in the periodical issues themselves, the vast majority of articles would remain outside our analytical scopes, since publishers did not provide (meaningful) bylines---most articles in {--both--} journals and newspapers from Baghdad, Beirut, Cairo or Damascus did not credit their authors.{>>The illegality of this behaviour is mentioned below<<} One approach would be to subject all articles to stylometric analysis for authorship attribution (more on this below) but this again presupposes truly *digital* editions.

<!-- identify the areas to catch up with -->

Note that a the full text of a periodical is necessary but not sufficient for many analytical queries and distant reading. It is certainly insufficient for close reading. The full text of a periodical would be nothing but a string of words. But periodicals unite different texts of various genres from multiple authors. These texts are commonly grouped into issues and volumes and longer ones were frequently serialised and scattered across issues. Some of these texts will be reprints from other periodicals or first printed publications of much older manuscripts. Some of the texts are responses, etc. In order to make sense of the full text of a periodical for both humans and machines it has to be modelled.

<!-- get the full text -->

Optical character recognition (OCR), the technology to convert an image into a text, has come a long way and even hand-written text recognition (HTR) is fairly successful at least for Latin script.[^9] Automatic recognition of Arabic script, however, is severely lacking behind for a variety of reasons beyond the scope of this paper.[^4] Despite promising developments with the application of machine-learning technologies to pattern recognition,[^7] automatic conversion of images of early Arabic periodicals is hampered by three factors: first, all OCR technologies depend on {--fairly large--} training sets of "gold standard" transcriptions as ground truth; second, low-quality fonts, inks, and paper employed at the turn of the twentieth century will inevitably result in poor print quality; and third, text recognition depends on layout recognition and multi-column texts with various intersections of boilerplate, ads, etc. pose serious challenges. Consequently these texts can currently only be reliably digitised by human transcription.[^12] Funds for transcribing the tens to hundreds of thousands of pages of an average mundane periodical are simply not available, despite of their cultural significance and unlike for valuable manuscripts and high-brow literature.

[^12]: The validity of this statement, of course, depends on the purpose of digitisation. If one was, for instance, interested in distant reading approaches to large corpora, such as the temporal distribution of certain keywords during a long print run, this would allow not just for aggregation on the issue level but probably even periods of full months and more. In consequence, error margins of almost one fourth in both Character Error Rate (CER) and Word Error Rate (WER) become seemingly acceptable; e.g. {Cristianini 2018@144}. Ryan Cordell argues for the importance of theorising the impact of OCR on scholarly findings. Cordell poses that OCR must be considered a new edition subject to "elaborate systems of scholarship, preservation, bureaucracy, human labor, machine processes, and economics"; {Cordell 2017@188}.

[^4]: C.f. {Märgner 2012a}. For recent promising approaches using machine-learning and neural networks see {Romanov_2016}. For examples of the state of Arabic OCR even for well-funded corporations and projects, try searching inside Arabic works on Google Books or HathiTrust. The ["Early Arabic Printed Books" (EAPB) project](http://gale.cengage.co.uk/arabic), currently under development by GALE in collaboration with the British Library, makes repeated claims of employing "newly developed optical character recognition software (OCR) for early Arabic printed script" (see this [factsheet](http://gale.cengage.co.uk/images/EAPB-Factsheet_English_WEB.pdf)). But since they share neither text layers nor error rates or software, their claims cannot be verified. As a substantial number of the digitised books in EAPB are written in languages other than Arabic that employ Arabic script (such as Farsī, Urdu or Ottoman Turkish) and as some works resemble complex manuscripts with multiple commentaries around a main text fully automated text-retrieval is highly unlikely.

[^7]: The [Open Islamicate Text Initiative (OpenITI)](http://iti-corpus.github.io/) project planned to publish its tool chain in 2018. For an overview of their work see <http://islamichistorycommons.org/mem/wp-content/uploads/sites/55/2017/11/UW-25-Savant-et-al.pdf>.

[^9]: One major research project for HTR is [Transkribus](https://transkribus.eu/Transkribus/). Sinai Rusinek and me have begun experimenting with submitting OpenArabicPE's editions as ground truth for training Transkribus. First results for single-column Arabic periodicals are promising and report a CER of less than 10 per cent, which would be sufficient for some distant reading applications.

Grey online-libraries of Arabic literature, namely [*al-Maktaba al-Shamila* (*shamela.ws*)][shamela], [*Mishkat*][almeshkat], [*Saydal-Fawa'id*][saaid] or [*al-Waraq*][alwaraq], provide access to a vast body of (mostly classical) Arabic texts including transcriptions of unknown provenance, editorial principals, and quality for some of the mentioned periodicals. These grey "editions" lack information linking the digital representation to material originals, namely bibliographic metadata and page breaks, which makes them almost impossible to employ for scholarly research.

Since we do not have the resources to proof and correct these texts, we had the idea to unite transcriptions from grey online libraries with the digital facsimiles from other sources as a means to verify the quality of the digital text. Thus "Open Arabic Periodical Editions" (OpenArabicPE) was born in autumn 2015.

# OpenArabicPE attempts at catching up

[OpenArabicPE](https://openarabicpe.github.io) establishes a framework for open, collaborative, and fully-referencable scholarly digital editions of early Arabic periodicals. The guiding principles of OpenArabicPE can be summarised as *accessibility*, *sustainability*, *credibility*. Starting with the mostly Damascene periodicals *al-Muqtabas* and *al-Ḥaqāʾiq*, OpenArabicPE demonstrates that one can produce scholarly editions that offer solutions for most of the above-mentioned problems---including the absence of expensive infrastructure---through re-purposing well-established open software platforms and by combining the virtues of immensely popular, but non-academic (and, at least under US copyright laws, occasionally illegal) online libraries of volunteers on the one hand with academic scanning efforts as well as editorial expertise on the other.

{--![Figure: Project scheme](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/OpenArabicPE-organigramme_horizontal.png)--}

Within OpenArabicPE we devise workflows and tools to transform digital texts from [*shamela.ws*][shamela] into an open, standardised file format (XML) following the [Text Encoding Initiative (TEI)](https://www.tei-c.org)'s guidelines,[^8] to generate bibliographic metadata, and to render a parallel display of text and facsimile in a web browser. We add light structural mark-up for articles, sections, authors, and bibliographic metadata, and link each page to facsimiles from various sources, namely [EAP][bl], [HathiTrust][hathitrust], and [archive.sakhrit.co][sakhrit].[^20] The latter step, in the process of which we also make first corrections to the transcription, though trivial, is the most labour-intensive because page breaks were commonly ignored by *shamela.ws*'s anonymous transcribers. This point needs to be emphasised: each of the c.8500 pages breaks in *al-Muqtabas* and *al-Ḥaqāʾiq* needed to be manually marked by volunteers in order to link facsimiles to the digital text and thus make the text verifiable for human readers.[^6] So far Dimitar Dragnev, Talha Güzel, Dilan Hatun, Hans Magne Jaatun, Xaver Kretzschmar, Daniel Lloyd, Klara Mayer, Tobias Sick, Manzi Tanna-Händel and Layla Youssef have contributed their time to this task.

[^6]: In other instances, such as the journals [*Lughat al-ʿArab*](https://github.com/OpenArabicPE/journal_lughat-al-arab), [*al-Ustādh*](https://github.com/OpenArabicPE/journal_al-ustadh)  or the [Yūsuf Ilyān Sarkīs' *Muʿjam al-maṭbūʿat al-ʿarabiyya wa-l-muʿarraba* (Miṣr: Maṭbaʿat Sarkīs, 1928)](http://shamela.ws/index.php/book/1242), *shamela.ws* did provide page breaks that correspond to a printed edition.
[^8]: TEI XML is the quasi-standard of textual editing and required by funding bodies and repositories for long-term archiving; cf. {DfgPraxisregelnDigitalisierung 2016}.
[^20]: Note that archive.sakhrit.co has since moved to [http://archive.alsharekh.org/](http://archive.alsharekh.org/)

{--![Figure: Web view of [al-Muqtabas 6/2](https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_61.TEIP5.xml)](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/boilerplate_muqtabas.png)--}

All tools and the editions are hosted on the code-sharing platform [GitHub](https://www.github.com) under MIT and Creative Commons [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/) licenses for reading, contribution, and re-use.[^10] {>>mention collaboration with Leipzig and the integration of Muqtabas into CLARIN<<} As part of the editions we provide structured bibliographic metadata for every article  in machine-readable format that can easily be integrated into larger bibliographic information systems{-- or individual scholars' reference managing software--}.[^26]

[^10]: We claim that text of {~~*al-Muqtabas* and *al-Ḥaqāʾiq* itself~>all periodicals in our corpus and originally published before 1920~~} is in the public domain even under the most restrictive definitions (i.e. in the USA); the anonymous original transcribers at *shamela.ws* do not claim copyright; and we only link to publicly accessible facsimile's without copying or downloading them. All code is archived on the Open Science platform [Zenodo](https://www.zenodo.org) that also provides stable identifiers (DOI) for every release.
[^26]: In addition, we make this data accessible through a constantly updated public [Zotero group](https://www.zotero.org/groups/OpenArabicPE).

With OpenArabicPE we argue that by linking facsimiles to the digital text, every reader can validate the quality of the transcription against the original. We thus remove the greatest limitation of crowd-sourced or grey transcriptions and the main source of disciplinary contempt among historians and scholars of the Middle East. Improvements of the transcription and mark-up can be crowd-sourced with clear attribution of authorship and version control using .git and GitHub's core functionality. Such an approach as proposed by Christian Wittern[^27] has recently seen a number of concurrent practical implementations such as project [GITenberg](https://gitenberg.github.io/) led by Seth Woodworth, Jonathan Reeve's [Git-lit](https://github.com/Git-Lit/git-lit), and others.

[^27]: {Wittern 2013}

{>>Some paragraphs on the importance of the two journals<<}


<!-- corpus -->
<!-- full editions -->
<!-- some information on al-Muqtabas -->

<!-- some information on al-Ḥaqāʾiq -->



<!-- bibliographic metadata -->

# Network of authors and texts

With major work on modelling both *al-Muqtabas* and *al-Ḥaqāʾiq* done, we can now begin to submit this corpus to initial analyses of the networks of authors and their texts as well as the material read and reviewed in Damascus.

## OpenArabicPE's corpus

The corpus comprises TEI files for each issue of *al-Muqtabas* and *al-Ḥaqāʾiq*. The edition of *al-Muqtabas* gathers all 96 issues published between 1906 and 1917/18 with a total of some 7.000 pages and almost 2 million words. {>>comment on publication dates<<} Issues consist of longer independent articles and sections with shorter articles such as brief reports on new discoveries and book announcements. Issues and pages differed widely in length. On average, each issue contained 65 pages with almost 300 words or 20354 word per issue.

![Figure: Words per page and page counts for *al-Muqtabas*](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/rplot_muqtabas-counts_words-pages-bars.png)

<!-- statistics on our editions -->

The edition of *al-Ḥaqāʾiq* comprises all 36 issues, grouped into three volumes and published by ʿAbd al-Qādir al-Iskandarānī in Damascus between 1910 and 1913. {>>comment on publication dates<<} Pages contain much less text and issues are much shorter than *al-Muqtabas* with a total of 300186 words across 1436 pages (as some 17 pages are missing from the transcription, the word count is too low). Save for a double issue, the vast majority of issues (28 of 36) comprised 40 pages with an average of slightly more than 200 words each. This results in an average 8577 words per issue compared to the 20354 words of *al-Muqtabas*.

![Figure: Words per page and page counts for *al-Ḥaqāʾiq*](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/rplot_haqaiq-counts_words-pages-bars.png)

<!-- state of the data -->

The quality and significance of the analysis is directly dependent on the quality of the information provided by the periodicals themselves and of our mark-up in the TEI source files. All relevant personal and place names in bylines and other source information must be marked up and linked to local and external authority files. References to authority files allow for the necessary disambiguation and grouping of entities that might be referenced by multiple names in our periodicals, such as "Rashīd Riḍā" and "Owner of al-Manār". In addition, by linking references to external authority files and the semantic web, we can harvest additional information on authors and locations, namely the geolocation for toponyms, transcriptions into Latin script necessary for working with most visualisation tools, and life dates for persons in order to establish the age of authors upon publication.{>>Comment on the issue of many visualisation tools, such as R and Gephi for macOS, not working with Arabic script<<}

## analysis of metadata

It is worth going back to the bibliographic metadata, its shortcomings and the resulting consequences for our analysis before looking at this aggregated information. *al-Muqtabas* printed a total of 2737 articles, 2020 of which were shorter articles in sections. Of the 717 independent articles, about two fifths (284) explicitly mentioned an author. Another 39 shorter articles carry bylines. The situation is similar at *al-Ḥaqāʾiq*: Only one fifth (76) of the 360 articles provide explicit author information. {>>add information on the number of words, which is more meaningful than the number of articles<<} We can currently identify only a maximum of 128 named authors for *al-Muqtabas* and less than 60 for *al-Haqāʾiq* [See word clouds below].[^5] Quite a significant number appear only with their initials, particularly in *al-Ḥaqāʾiq* and all of them were men. Only 50 authors published more than one article in *al-Muqtabas*. Two of the four most prolific authors with more than ten bylines to their names wrote from Baghdad (See table below): Maʿrūf al-Ruṣāfī (24 articles) and Buṭrus bin Jibrāʾīl Yūsuf ʿAwwād, using the pen name Sātisnā (14). ʿĪsā Iskandar al-Maʿlūf (20) wrote mostly from Zaḥle and Yūsuf Jirjis Zakham (13) from Omaha and Lincoln, Nebraska, USA. Only the fifth most prolific author was a native resident of Damascus: Jamāl al-Dīn al-Qāsimī (8). {>>add comments on genre of texts by these authors<<}

<!-- The majority of the remaining authors contributed from the cities of Greater Syria and Egypt, but some wrote from cities in France. -->

[^5]: These word clouds were produced with R on macOS. Take note that most visualisations in R for macOS---unlike Windows or Linux---cannot correctly display Arabic script.

<!-- Muqtabas: authors by byline -->

| author.id                                                                   | author.name                           | author.birth   | author.death   | works.viaf.count   | article.count   | word.count   |
| --------------------------------------------------------------------------- | ------------------------------------- | -------------- | -------------- | ------------------ | --------------- | ------------ |
| [viaf:14924300](https://viaf.org/viaf/14924300)                             | معروف الرصافي                         | 1875-01-01     | 1945-01-01     | 36                 | 24              | 12438        |
| [viaf:40250618](https://viaf.org/viaf/40250618)                             | عيسى أفندي اسكندر المعلوف             | 1869-04-11     | 1956-07-02     | 26                 | 20              | 23297        |
| [viaf:39370998](https://viaf.org/viaf/39370998)                             | ساتسنا                                | 1866-08-05     | 1947-01-07     | 55                 | 14              | 19844        |
|                                                                             | يوسف جرجس زخم                         |                |                |                    | 12              | 19638        |
| [viaf:93607460](https://viaf.org/viaf/93607460)                             | جمال الدين القاسمي                    | 1866-10-01     | 1914-04-18     | 67                 | 8               | 38531        |
|                                                                             | إبراهيم حلمي العمر                    |                |                |                    | 8               | 20117        |
| [viaf:32272677](https://viaf.org/viaf/32272677)                             | Muḥammad Kurd ʿAlī                    | 1876-01-01     | 1953-01-01     | 58                 | 7               | 42488        |
| [viaf:49218655](https://viaf.org/viaf/49218655)                             | أحمد بك زكي                           | 1866-05-26     | 1934-07-06     | 62                 | 7               | 40311        |
| [viaf:22006374](https://viaf.org/viaf/22006374)                             | محمد رضا الشبيبي                      | 1889-01-01     | 1965-01-01     | 13                 | 7               | 17870        |
| [viaf:118432135](https://viaf.org/viaf/118432135)                           | عبد القادر أفندي المغربي              | 1867           | 1956-06-07     | 12                 | 7               | 14074        |
| [viaf:28125663](https://viaf.org/viaf/28125663)                             | رفيق بك العظم                         | 1865-01-01     | 1925-06-30     | 21                 | 7               | 13237        |
| [viaf:19737865](https://viaf.org/viaf/19737865)                             | أحمد بك تيمور                         | 1871-11-06     | 1930           | 63                 | 7               | 7899         |
| [viaf:305214884](https://viaf.org/viaf/305214884)                           | جرجي حداد                             |                |                | 0                  | 5               | 24124        |
| [viaf:299037057](https://viaf.org/viaf/299037057)                           | عبد الله أفندي مخلص                   | 1878           | 1947           | 10                 | 5               | 13494        |
|                                                                             | خليل سعد                              |                |                |                    | 5               | 5932         |

Table: The fifteen most prolific authors in *al-Muqtabas* by number of bylines.

{>>Further comments on this table:
    1. all but one of the most frequently published authors have entries in authority files and wikipedia
    2. data from the authority files shows that all but one were born between the mid-1860s and the mid-1870s
<<}

![Figure: Word cloud of authors published in *al-Muqtabas*; by number of articles](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/word-cloud_muqtabas-authors-bylines.png)

{>>al-Ḥaqāʾiq<<}

| author.id                                                                   | author.name                                  | author.birth   | author.death   | works.viaf.count   | article.count   | word.count   |
| --------------------------------------------------------------------------- | -------------------------------------------- | -------------- | -------------- | ------------------ | --------------- | ------------ |
|                                                                             | إبراهيم خليل مردم بك                         |                |                |                    | 6               | 4702         |
| [viaf:53094077](https://viaf.org/viaf/53094077)                             | محمد فريد أفندي وجدي                         | 1875           | 1954           | 54                 | 5               | 8344         |
| [viaf:299025643](https://viaf.org/viaf/299025643)                           | محمد عارف المنير الحسيني                     | 1847/48        |                | 2                  | 5               | 3151         |
|                                                                             | عبد الرحمن القصار                            |                |                |                    | 5               | 1429         |
| [viaf:58892856](https://viaf.org/viaf/58892856)                             | الشيخ صالح أفندي الشريف                      | 1869           | 1920           | 8                  | 4               | 5000         |
| [viaf:267054449](https://viaf.org/viaf/267054449)                           | مختار المؤيد                                 | 1822           | 1921           | 2                  | 4               | 949          |
|                                                                             | أبو الضيا                                    |                |                |                    | 3               | 5097         |
|                                                                             | أحمد الباشا                                  |                |                |                    | 3               | 4274         |
|                                                                             | ع                                            |                |                |                    | 3               | 2833         |
|                                                                             | صلاح الدين الزعيم                            |                |                |                    | 3               | 2448         |
|                                                                             | محمد القاسمي الحلاق                          |                |                |                    | 2               | 3619         |
| [viaf:17087051](https://viaf.org/viaf/17087051)                             | محمد أبو الخير الطباع                        |                |                | 1                  | 2               | 2881         |
| [viaf:63117968](https://viaf.org/viaf/63117968)                             | محمد راغب طباخ                               | 1877           | 1951           | 10                 | 2               | 1445         |
|                                                                             | عبد المجيد القصاب                            |                |                |                    | 2               | 1405         |
|                                                                             | أحمد الجوبري                                 |                |                |                    | 2               | 1113         |

Table: The fifteen most prolific authors in *al-Ḥaqāʾiq* by number of bylines

![Figure: Word cloud of authors published in *al-Ḥaqāʾiq*](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/word-cloud_haqaiq-authors-bylines.png)

## going beyond bibliographic metadata

We can easily add another dimension to our analysis of the authors published in *al-Muqtabas* and *al-Ḥaqāʾiq*. One could argue that, within genre boundaries, the number of texts is less significant for the relative importance of an author than the total length of all texts by a single author. With access to the full text with structural mark-up, we can easily calculate word counts. Muḥammad Kurd ʿAlī himself would immediately become the most important author (see table below) due to his lengthy reports from a journey across Europe, which he later published as a collection titled *Gharāʾib al-gharb*. He would be followed by Aḥmad Zakī (Pasha), an important Egyptian philologist and politician, and by Jamāl al-Dīn al-Qāsimī. Also included in this list of the ten most prolific authors published in *al-Muqtabas*, is Ibn al-Muqaffaʿ (d.759), the famous author of *Kalīla wa dhimna*, which points to an important function of *al-Muqtabas*: the publication of hitherto unpublished manuscripts and the re-print of classics. This is also attested to by the presence of Aḥmad (Bey) Taymūr in the above list of most important authors by number of articles. An avid collector of manuscripts, Aḥmad Taymūr provided many such manuscript to Muḥammad Kurd ʿAlī for publication and he frequently wrote the introductions.

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

Table: authors in *al-Muqtabas* sorted by number of words.

![Figure: Word cloud of authors published in *al-Muqtabas*; by number of words](https://github.com/OpenArabicPE/slides/raw/gh-pages/assets/plots/word-cloud_muqtabas-authors-words.png)

*al-Muqtabas* and *al-Ḥaqāʾiq*, like any other periodical at the time, seriously violated the Ottoman press code that required identifiable author information being published alongside each article.{>>add footnote with comment and reference to sources<<} This also means that any analysis of bibliographic information is based on only a small sample of either periodical.

# Stylometry

What are the consequences of such a severe lack of information and are there means of filling the gap? One obvious approach to follow would be to submit the entire corpus to stylometric analysis. Stylometry is one of the methods frequently referred to as *distant reading*.[^13]  It can be summarised as the statistical analysis of literary style for the purpose of authorship attribution and genre detection, whereby "style" commonly means a frequency count of vocabulary used in a given text.[^11] Stylometry is based on the empirical observation "that authors tend to write in relatively consistent, recognizable and unique ways"[^14] which is particularly true for an author's vocabulary. Stylometry then computes degrees of similarity between texts, called distance measure, through {--various methods of --}comparing multivariant frequency lists of textual features. 

{==This is not the space to discuss the intricacies of stylometry for authorship attribution, the available tools and the necessary amount of pre-processing to be applied to Arabic texts before submitting them to stylometric analysis.==}{>>It definitely is and this needs to be done here<<} The important catch here is that in order to establish similarities, one has to have access to a significant corpus of digital texts by authors likely to be found among the unattributed texts. If we only compare every article in our periodical corpus to every other article in the same corpus, we cannot possibly identify any author not yet named in a byline. Instead, the best we could hope for would be to establish groups of texts that have a certain likelihood of having been authored by the same person.

[^14]: {Laramée 2018}

[^13]: For a good summary of genealogy of large-scale literary history under the label "distant reading" see {Underwood 2017}. The most often referenced founding works are {Moretti 2013} (collection of reprinted essays), {Jockers 2013} {>> Jockers, Underwood<<}.

[^11]: For an introduction to stylometry see {>>add references<<}

## my methodology

All stylometric analysis in this paper was done using the "stylo" package for R.[^15]

[^15]: {Eder 2016b}

## first results 

Our initial submission of a corpus of all articles published by *al-Muqtabas* to stylometric analysis using a comparison of the 1000 most-frequent words (MFWS) and without any preprocessing of the Arabic---such as morphologising or lemmatizing---show mixed results. Whereas a comparison of articles known to have been authored by Jamāl al-Dīn al-Qasimī shows a high degree of similarity with other articles written by him and therefore seemingly confirms the correct working of the algorithms, this is not the case for either Maʿrūf al-Ruṣāfī or ʿĪsā Iskandar al-Maʿlūf. This is puzzling as the degree of likeliness for the top-most stylistically similar articles by al-Maʿlūf, expressed by the weight in the tables below, is in the same range as for those by al-Qāsimī.

|                    source                   |                    target                   | weight |    type    |
|---------------------------------------------|---------------------------------------------|--------|------------|
| القاسمي-oclc_4770057679-i_61-div_2.d1e1517  | القاسمي-oclc_4770057679-i_62-div_2.d1e1491  |     54 | undirected |
| القاسمي-oclc_4770057679-i_62-div_2.d1e1491  | القاسمي-oclc_4770057679-i_61-div_2.d1e1517  |     54 | undirected |
| القاسمي-oclc_4770057679-i_61-div_2.d1e1517  | القاسمي-oclc_4770057679-i_63-div_7.d1e1810  |     52 | undirected |
| القاسمي-oclc_4770057679-i_63-div_7.d1e1810  | القاسمي-oclc_4770057679-i_61-div_2.d1e1517  |     52 | undirected |
| القاسمي-oclc_4770057679-i_49-div_2.d1e1499  | NN-oclc_4770057679-i_48-div_4.d1e1914       |     45 | undirected |
| القاسمي-oclc_4770057679-i_62-div_2.d1e1491  | القاسمي-oclc_4770057679-i_63-div_7.d1e1810  |     44 | undirected |
| القاسمي-oclc_4770057679-i_63-div_7.d1e1810  | القاسمي-oclc_4770057679-i_62-div_2.d1e1491  |     44 | undirected |
| القاسمي-oclc_4770057679-i_52-div_10.d1e2681 | القاسمي-oclc_4770057679-i_53-div_3.d1e3775  |     42 | undirected |
| القاسمي-oclc_4770057679-i_53-div_3.d1e3775  | القاسمي-oclc_4770057679-i_52-div_10.d1e2681 |     42 | undirected |
| القاسمي-oclc_4770057679-i_50-div_4.d1e2033  | القاسمي-oclc_4770057679-i_63-div_7.d1e1810  |     38 | undirected |
| القاسمي-oclc_4770057679-i_63-div_7.d1e1810  | القاسمي-oclc_4770057679-i_50-div_4.d1e2033  |     38 | undirected |
| القاسمي-oclc_4770057679-i_49-div_2.d1e1499  | NN-oclc_4770057679-i_47-div_2.d1e1470       |     31 | undirected |
| القاسمي-oclc_4770057679-i_55-div_23.d1e4814 | NN-oclc_4770057679-i_2-div_21.d1e2160       |     24 | undirected |
| القاسمي-oclc_4770057679-i_49-div_2.d1e1499  | NN-oclc_4770057679-i_87-div_3.d1e696        |     24 | undirected |
| القاسمي-oclc_4770057679-i_50-div_4.d1e2033  | NN-oclc_4770057679-i_64-div_2.d1e1188       |     24 | undirected |
| القاسمي-oclc_4770057679-i_63-div_7.d1e1810  | NN-oclc_4770057679-i_15-div_3.d1e696        |     18 | undirected |
| القاسمي-oclc_4770057679-i_49-div_2.d1e1499  | NN-oclc_4770057679-i_19-div_9.d1e2206       |     17 | undirected |
| القاسمي-oclc_4770057679-i_55-div_23.d1e4814 | NN-oclc_4770057679-i_3-div_18.d1e1764       |     16 | undirected |
| القاسمي-oclc_4770057679-i_61-div_2.d1e1517  | NN-oclc_4770057679-i_33-div_3.d1e696        |     16 | undirected |
| القاسمي-oclc_4770057679-i_39-div_7.d1e2166  | عنحوري-oclc_4770057679-i_54-div_2.d1e1300   |     15 | undirected |

Table: Selection of results from the stylometric analysis of all articles published in *al-Muqtabas* based on 1000 MFWs where the source was authored by Jamāl al-Dīn al-Qāsimī



|                    source                   |                 target                 | weight |    type    |
|---------------------------------------------|----------------------------------------|--------|------------|
| الرصافي-oclc_4770057679-i_10-div_9.d1e1418  | NN-oclc_4770057679-i_94-div_11.d1e5944 |     27 | undirected |
| الرصافي-oclc_4770057679-i_24-div_9.d1e1716  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     27 | undirected |
| الرصافي-oclc_4770057679-i_36-div_5.d2e3004  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     27 | undirected |
| الرصافي-oclc_4770057679-i_20-div_6.d1e1588  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     26 | undirected |
| الرصافي-oclc_4770057679-i_19-div_6.d1e1081  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     25 | undirected |
| الرصافي-oclc_4770057679-i_28-div_25.d1e3388 | NN-oclc_4770057679-i_2-div_21.d1e2160  |     25 | undirected |
| الرصافي-oclc_4770057679-i_37-div_7.d1e1907  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     25 | undirected |
| الرصافي-oclc_4770057679-i_40-div_14.d1e2780 | NN-oclc_4770057679-i_94-div_11.d1e5944 |     25 | undirected |
| الرصافي-oclc_4770057679-i_13-div_9.d1e1285  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     24 | undirected |
| الرصافي-oclc_4770057679-i_14-div_7.d1e1428  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     24 | undirected |
| الرصافي-oclc_4770057679-i_22-div_9.d1e1772  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     24 | undirected |
| الرصافي-oclc_4770057679-i_31-div_10.d1e2096 | NN-oclc_4770057679-i_2-div_21.d1e2160  |     24 | undirected |
| الرصافي-oclc_4770057679-i_39-div_5.d1e1387  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     24 | undirected |
| الرصافي-oclc_4770057679-i_41-div_7.d1e3728  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     24 | undirected |
| الرصافي-oclc_4770057679-i_25-div_11.d1e2206 | NN-oclc_4770057679-i_2-div_21.d1e2160  |     23 | undirected |
| الرصافي-oclc_4770057679-i_29-div_6.d1e1333  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     23 | undirected |
| الرصافي-oclc_4770057679-i_40-div_4.d1e832   | NN-oclc_4770057679-i_2-div_21.d1e2160  |     21 | undirected |
| الرصافي-oclc_4770057679-i_33-div_5.d1e1329  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     20 | undirected |
| الرصافي-oclc_4770057679-i_35-div_3.d1e696   | NN-oclc_4770057679-i_2-div_21.d1e2160  |     20 | undirected |
| الرصافي-oclc_4770057679-i_68-div_9.d1e4370  | NN-oclc_4770057679-i_2-div_21.d1e2160  |     20 | undirected |

Table: Selection of results from the stylometric analysis of all articles published in *al-Muqtabas* based on 1000 MFWs where the source was authored by Maʿrūf al-Ruṣāfī




|                    source                   |                   target                   | weight | type           |
|---------------------------------------------|--------------------------------------------|--------|------------|
| المعلوف-oclc_4770057679-i_53-div_2.d1e1568  | NN-oclc_4770057679-i_64-div_3.d1e2089      |     47 | undirected |
| المعلوف-oclc_4770057679-i_53-div_2.d1e1568  | NN-oclc_4770057679-i_35-div_6.d1e2205      |     32 | undirected |
| المعلوف-oclc_4770057679-i_37-div_10.d1e3397 | NN-oclc_4770057679-i_2-div_21.d1e2160      |     27 | undirected |
| المعلوف-oclc_4770057679-i_42-div_9.d1e1281  | NN-oclc_4770057679-i_23-div_25.d1e2996     |     26 | undirected |
| المعلوف-oclc_4770057679-i_53-div_2.d1e1568  | NN-oclc_4770057679-i_56-div_2.d1e1398      |     26 | undirected |
| المعلوف-oclc_4770057679-i_55-div_10.d1e2970 | NN-oclc_4770057679-i_2-div_21.d1e2160      |     26 | undirected |
| المعلوف-oclc_4770057679-i_93-div_8.d1e1268  | NN-oclc_4770057679-i_2-div_21.d1e2160      |     26 | undirected |
| المعلوف-oclc_4770057679-i_54-div_5.d1e1854  | NN-oclc_4770057679-i_2-div_21.d1e2160      |     25 | undirected |
| المعلوف-oclc_4770057679-i_94-div_11.d1e6080 | NN-oclc_4770057679-i_2-div_21.d1e2160      |     25 | undirected |
| المعلوف-oclc_4770057679-i_95-div_51.d1e3324 | NN-oclc_4770057679-i_2-div_21.d1e2160      |     25 | undirected |
| المعلوف-oclc_4770057679-i_44-div_6.d1e1798  | NN-oclc_4770057679-i_2-div_21.d1e2160      |     24 | undirected |
| المعلوف-oclc_4770057679-i_45-div_8.d1e2304  | NN-oclc_4770057679-i_2-div_21.d1e2160      |     24 | undirected |
| المعلوف-oclc_4770057679-i_47-div_6.d1e2816  | NN-oclc_4770057679-i_2-div_21.d1e2160      |     24 | undirected |
| المعلوف-oclc_4770057679-i_55-div_22.d1e4313 | NN-oclc_4770057679-i_2-div_21.d1e2160      |     24 | undirected |
| المعلوف-oclc_4770057679-i_93-div_7.d1e1147  | NN-oclc_4770057679-i_2-div_21.d1e2160      |     24 | undirected |
| المعلوف-oclc_4770057679-i_53-div_33.d1e6920 | NN-oclc_4770057679-i_2-div_21.d1e2160      |     23 | undirected |
| المعلوف-oclc_4770057679-i_63-div_30.d1e2971 | NN-oclc_4770057679-i_2-div_21.d1e2160      |     21 | undirected |

Table: Selection of results from the stylometric analysis of all articles published in *al-Muqtabas* based on 1000 MFWs where the source was authored by ʿĪsā Iskandar al-Maʿlūf


# Geographic distribution

Successful stylometric authorship attribution, will not fill the gap in geographic information in all but the most obvious and likely case, namely that a large part of the unattributed articles were indeed written by a periodical's editor. In the case of *al-Muqtabas*, we know the whereabouts of Muḥammad Kurd ʿAlī during most of the time he published the journal and could thus easily assign locations to articles. However, given that we are interested in the *network* of authors, texts, and locations, this would be an utterly pointless endeavour.

If we assume that information on the place of writing of any one article was not generally considered sensitive information to be protected in all but the most harmless cases and that most articles where authored by the publishers and at the place of publication, one can nevertheless arrive at a meaningful picture of the geographic distribution of authors and the origin of articles:

![Figure: Locations in bylines in *al-Muqtabas* (Cairo and Damascus)](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/visualization/maps/map-oclc_4770057679-bylines-middle-east.png)

![Figure: Locations in bylines in *al-Ḥaqāʾiq* (Damascus)](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/visualization/maps/map-oclc_644997575-bylines-middle-east.png)

![Figure: Locations in bylines in *al-Ḥasnāʾ* (Beirut)](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/visualization/maps/map-oclc_792756327-bylines-middle-east.png)

![Figure: Locations in bylines in *Lughat al-ʿArab* (Baghdad)](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/visualization/maps/map-oclc_472450345-bylines-middle-east.png)


{>>missing comment on maps<<}

# Network of referenced periodicals

![Figure: Network of periodicals mentioned in *al-Haqāʾiq*, *al-Muqtabas* and *Lughat al-ʿArab*](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/visualization/networks/network_oape-referenced-periodicals.png)

![](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/visualization/networks/network_oape-referenced-periodicals-per-article_2019-08-16.png)

![](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/visualization/networks/network_oape-referenced-periodicals-per-issue_2019-08-16.png)

{>>missing conclusion<<}

[almeshkat]: http://almeshkat.net/
[alwaraq]: http://www.alwaraq.net/
[bibalex]: http://ima.bibalex.org/IMA/presentation/home/list.jsf
[menadoc]: http://menadoc.bibliothek.uni-halle.de/
[bl]: http://eap.bl.uk/
[hathitrust]: http://catalog.hathitrust.org/
[openarabicpe_schema]: https://github.com/OpenArabicPE/OpenArabicPE_ODD
[rawgit]: https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_54.TEIP5.xml#pb_61.d1e2036
[rawgit 2]: https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_59.TEIP5.xml#pb_51.d1e2281
[rawgit 3]: https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_38.TEIP5.xml#p_60.d1e2238
[rawgit 4]: https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_39.TEIP5.xml#gap_1.d1e3111
[rawgit 5]: https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_71.TEIP5.xml#pb_126.d1e4373
[saaid]: http://saaid.net/
[sakhrit]: http://archive.sakhrit.co
[shamela]: http://www.shamela.ws/
[shamela 2]: http://shamela.ws/index.php/book/26523
[wikisource]: https://ar.wikisource.org/wiki/%D9%85%D8%AC%D9%84%D8%A9_%D8%A7%D9%84%D9%85%D9%82%D8%AA%D8%A8%D8%B3/%D8%A7%D9%84%D8%B9%D8%AF%D8%AF_1
