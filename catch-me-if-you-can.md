---
title: "Catch me if you can! Computational approaches to track the late Ottoman ideosphere of authors and periodicals in the wasteland of the 'digitised' Arabic press"
author: Till Grallert
date: 2019-11-01
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
<!-- pre-process with pancritic and use crossref -->
<!-- ## 1. HTML -->
<!-- pancritic catch-me-if-you-can.md -t markdown --critic-mode accept | pandoc -F pandoc-crossref -s -f markdown -t html5-smart --toc --include-in-header=/BachUni/programming/Pandoc/css-pandoc_online-publication.txt --include-in-header=/BachUni/programming/Pandoc/css-pandoc_code-highlight_oxygen-xml.txt --email-obfuscation=javascript -o index.html -->
<!-- ## 2. DOCX -->
<!-- pancritic catch-me-if-you-can.md -t markdown --critic-mode accept | pandoc -F pandoc-crossref -s -f markdown -t docx-smart -o catch-me-if-you-can.docx -->

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

# About

>This paper originated in a presentation at Turkologentag 2018 in Bamberg, Germany, 19--21 September 2018. The computational analysis was first presented at the international workshop "Creating Spaces, Connecting Worlds: Dimensions of the Press in the Middle East and Eurasia" in Zurich, 31 October -- 2 November 2019. The final version is meant for submission to a special issue of "Geschichte und Gesellschaft".

>The current stable draft of this paper is version [v0.2](https://tillgrallert.github.io/p3a6afa20/v0-2/index.html) and contains unprocessed references to sources and secondary literature, cross-references, and CriticMarkup. To comment / review / annotate this version via hypothes.is click [here](https://via.hypothes.is/https://tillgrallert.github.io/p3a6afa20/v0-2/index.html). The most recent changes are available [here](https://tillgrallert.github.io/p3a6afa20/index.html).

>Note that network plots currently make use of a computational transcription of Arabic into Latin script. The intended general audience is assumed to not be able to read Arabic. Since the latest version of macOS Mojave and Gephi 0.9.2 finally render Arabic script in network scripts, I shall supply a secondary set of Arabic plots.

# Introduction

This paper presents the dual challenge of {=="digital history"==} to the study of the ideosphere of the late Ottoman Eastern Mediterranean[^53] through its periodical press. The first challenge is to confront hyperbolic promises of mass digitisation and computational methods for the exploration of digitised cultural heritage as a hegemonic episteme rooted in 20th-century, english-speaking, neoliberal capitalism from the margins---That is, the study of a historical multilingual society whose material heritage has been looted, destroyed and neglected. A society, whose material heritage resists digitisation efforts by being dependent on non-Latin scripts and, for instance, non-Gregorian calendars. A society, whose contemporary heirs cannot draw on the vast resources in wealth and socio-technical infrastructures of the Global North. 

The second challenge is to actually explore the ideosphere of periodicals and their contributors{>> through computational approaches such as network analysis and stylometry<<}. The Arabic periodical press of the late Ottoman Eastern Mediterranean{--[^53]--} has received scholarly attention since the early twentieth century. Early Arabic periodicals {--from the late nineteenth and early twentieth centuries,--} such as Butrus al-Bustānī's *al-Jinān* (Beirut, 1876–86), Yaʿqūb Ṣarrūf, Fāris Nimr, and Shāhīn Makāriyūs' *al-Muqtaṭaf* (Beirut and Cairo, 1876–1952), Muḥammad Kurd ʿAlī's *al-Muqtabas* (Cairo and Damascus, 1906–18/19) or Rashīd Riḍā's *al-Manār* (Cairo, 1898–1941) are at the core of formative discourses that still reverberate through the Arabic-speaking Middle East: the Arabic (cultural) renaissance (*nahḍa*), Arab nationalism, and the Islamic reform movement (*ṣalafiyya*). Yet, core questions concerning the intellectual history of the periodical press and the social history of periodical production are still unanswered. Arabic approaches to the periodical press have been, for a long time, both encyclopaedic and anecdotal as well as biased by an almost exclusive focus on Cairo and Beirut. Many of these works were compiled by authors who themselves were journalist and adhere to a specific political view of Arab nationalism and demonize the Ottoman Empire, particularly during the reign of ʿAbdülḥamīd II (1876--1909).[^28] Non-Arabic scholarship commonly perceives of journals and newspapers as a *source* for intellectual, social and political history but only rarely as a *subject* in its own right. There is the noteworthy exception of Ami Ayalon's extensive writings on the press in the Arab Middle East[^31], but comprehensive, synthesising approaches are severely limited by the almost complete absence of systematic studies on individual periodicals.[^17] Even scholarly approaches to the press as a *source* remain largely anecdotal with a focus on opinion pieces and editorials in a small sample of canonical journals from Beirut and Cairo. The main reasons are scale and scattered collections, which, however, remain {==completely==}{>>largely<<} unacknowledged.

[^28]: E.g. {Jundī 1925; Shaykhū 1926; Sarkīs 1929}, {Muruwwa 1961; AlRifāʿī 1969; AlRifāʿī 1969a; Dāghir 1950; Dāghir 1978; Ilyās 1982; Khūrīya 1976}

{>>Bibliographies: {AhmedBioud 1969}<<}

[^31]: {Ayalon 1995}; {Ayalon 1984; Ayalon 1985; Ayalon 1987a; Ayalon 1987; Ayalon 1992; Ayalon 2002; Ayalon 2008}.

[^53]: Late Ottoman Eastern Mediterranean is a lose moniker for the pre-dominantly Arabic speaking provinces of the Ottoman Empire along the eastern shore of the Mediterranean between the mountains of Anatolia in the north, Mesopotamia in the east, the deserts of the Arabian Peninsula in the south and the Lybian desert in the west. The area is largely congruent with *al-Mashriq* or the Arab East and Egypt.
{--Adana to Egypt, the Fertile Crescent and the Arabian Peninsula, encompassing the modern countries (or parts thereof) of Turkey, Syria, Lebanon, Palestine, Israel, Jordan, Egypt, Sudan, Iraq, Saudi Arabia and Yemen.--} The period is delineated by the advent of the press (c.1860) and the collapse of Ottoman rule with the end of WW I (1918).

[^17]: Exceptions are {Glaß 2004b;Cioeta 1979a}{Cioeta 1979}. {--At the time of writing, only one study made use of digital texts: {Zemmin 2018}; for methodological comments see also {Zemmin 2016@232-233}.--} {>>Add comment on {Dierauff 2018}{Beška 2017}<<}


{>>the following section needs rewriting<<}

In consequence, we still need to answer questions such as: What are the core nodes (authors, periodicals, other works) in the ideosphere of the late Ottoman Eastern Mediterranean? Is the geographic bias of Cairo and Beirut justified if we look at more than the "easily" accessible handful of monthly journals mentioned above? How would we need to re-write the intellectual history of the final decades of the Ottoman Empire if the myriad of papers and their contributors from places as far as Algiers, Basra or Aleppo were included? The answers to these questions depend on another set of questions: Who authored the majority of articles in any one periodical that did not carry a byline? Can we confirm the common---and untested---assumption that the proprietor or editor-in-chief mentioned in a journal's imprint or a newspaper's masthead just authored all the anonymous texts themselves? {>>Even if they were absent from the place of publication for prolonged periods of time, as we know they repeatedly were?<<} Is it true, as some suspect, that editors invented contributors to their journals from far-away places to impress their audiences?

{>>the following can remain: summary<<}

This paper explores the late Ottoman ideosphere of the Eastern Mediterranean through the question of authorship and references to other periodical titles and the resulting intellectual, social and geographic networks. It presents a first foray into computational approaches to these questions by adopting methods broadly summarised as *distant reading*, namely social network analysis and stylometry. {--Computational methods depend on digital corpora. --}I start by contrasting the hyperbolic promises of digitisation with the bleak reality of extremely limited access to unsystematically digitised facsimile corpora of Arabic periodicals from the late Ottoman Eastern Mediterranean. A socio-technical infrastructure built upon English and Latin script as the hegemonic technical paradigm, I argue, contributes to a neo-colonial divide between the abundance of digitised cultural artefacts of the Global North and the invisibility of almost anything beyond. This necessitates substantial corpus building efforts for many scholars working on texts in non-Western languages written in non-Latin scripts and severely limits the scope of our computational scrutiny.

I introduce my corpus-building project [OpenArabicPE](https://openarabicpe.github.io) as a framework to unite transcriptions of a small number of early twentieth-century periodicals from grey online platforms with digital facsimiles for the purpose of validating the former. Consequently, any corpus built {==with these affordances==}{>>better wording<<} and the dependence on the work of anonymous others will not be systematically tailored to the research questions one might have. After substantial modelling efforts, I am now able to generate and analyse bibliographic datasets as well as run first stylometric analyses on this corpus of some 165 periodical issues of c. 2.65 million words.  Although the approach can by no means be characterised as distant reading of big data, it is the first systematic attempt to empirically answer core questions for the nascent field of Arabic periodical studies, which are in turn indispensable for a proper source critique if one wanted to employ these periodicals for the historiography of the late Ottoman Eastern Mediterranean. 

{>>add paragraph summarising my results: The geographic realm must be broadened to at least include Iraq but also Sudan (as in the case of *al-Zuhūr*, which doesn't feature in this paper)<<}

# The promised land of *digitised* Arabic periodicals

The better known and at the time widely popular Arabic journals of the late Ottoman Empire---unlike their smaller rivals and more ephemeral newspaper copies---do not face the ultimate danger of their last copy being destroyed in the current onslaught from iconoclasts, institutional neglect, and wars raging through Syria, Libya, Yemen, and Iraq. Yet, copies are scattered across libraries and institutions worldwide. This makes it almost impossible to trace discourses across journals and with the demolition and closure of libraries in the Middle East, they are increasingly accessible to the affluent Western researcher only.

A quick look at *al-Muqtabas* shall  illustrate this point. A search in [WorldCat](https://www.worldcat.org) for the nine volumes of *al-Muqtabas*  will return six different bibliographic entries, the first of which has 13 variants (called "editions" in the context of WorldCat), pointing to 34 libraries. If one follows each entry to the holding library's catalogue, one will find that the large majority of collections is incomplete and that collections commonly combine original volumes, reprints, microfilms, microfiches and even photo copies. {>>comment on the geographic distribution of collections: the map below shows a surprising distribution of copies, which could either be due to Worldcat's bias towards western collections or a reflection of actual holdings. But even for regions with good coverage, such as central Europe, we can attest that interested readers would need to travel or depend on interlibrary loans to excess every issue of *al-Muqtabas*.<<}

![Figure: geographic distribution of library holdings of *al-Muqtabas*](assets/plots/map-oclc_4770057679-holdings-vol_1-9.png)

Digitisation promises an "easy" solution to the problems of preservation and access. Instant access to tens if not hundreds of thousands of *digitised* periodical issues from the late Ottoman Empire evokes the gold rush in the American west and many people imagine a promised land of instantaneous one-click answers to any question they might have.
The public and many scholars expect to be able to put a computer to such diverse tasks as a keyword search: Show me all instances of the word *waṭan* (Arabic for "homeland", "nation") across the ideosphere of the early Arabic press between Morocco and Iraq from its beginnings until the World War I.[^56] Or a social network analysis: Show me the discursive field of authors and their texts and its changes over time. These are important and---for a variety of reasons, some of which will be discussed in this article---still open questions. Unfortunately, the eager student of *digitised* Arabic periodicals will immediately find tools, data and skills lacking.

[^56]: The almost hegemonic interface to digitised collections incorporates focusses on a Google-like search bar and makes browsing titles---the classic way of accessing periodicals---nigh impossible. The de-contextualising of strings of text from the page and the wider context of the periodical immanent to keyword search has been repeatedly criticised as inadequate for the study of periodicals; e.g. {Brake 2012a}{Brake 2012@17}{Bingham 2010@229-230}{Gooding 2018@12-13}.

<!-- problem: there is no big data. on the difference between *digitised* and *digital* -->

The first question we encounter in our attempt to track the network of authors and texts is to which extent can we submit *digitised* periodicals to computational analysis, or rather, what is the meaning of *digitised* and *access*? The answer is, of course, very different from periodical corpora in Western languages. It is sobering and will put off but the most enthusiastic readers: from large corporate and institution-backed platforms[^1] to grey online libraries[^2] *digitised* in the context of Arabic and Ottoman periodicals commonly means nothing more than the provision of digital facsimiles. Some platforms, such as [Hathitrust](http://catalog.hathitrust.org/) and [Cengage Gale](http://gale.cengage.co.uk/arabic.aspx), include search functions, but these are extremely limited. The former, Google-powered, platform is obviously dysfunctional for Arabic text if one has a look at the text layer. The latter claims it employed "[n]ewly-developed optical character recognition software (OCR) for early Arabic printed script"[^18] but does not make the text layer accessible to scrutiny. We will therefore never know the extent of false negatives (one can manually check for false positives by going through the search results). Beyond copyright, *access* to these *digitised facsimiles* is always restricted to viewing individual pages in web interfaces and limited by subscription fees and membership of specific academic institutions.[^3] To computationally answer the above questions, however, one would need unrestricted access to truly *digital* editions---that is, machine-readable editions of the full text with embedded structural and semantic information and in a standardised exchange format.[^19]

[^1]: Such as [Cengage Gale](http://gale.cengage.co.uk/arabic.aspx), [Hathitrust](http://catalog.hathitrust.org/), the [British Library's "Endangered Archives Programme" (EAP)](http://eap.bl.uk/), [MenaDoc](http://menadoc.bibliothek.uni-halle.de/), ["*Jarāyid*: Arabic newspaper archive of Ottoman and Mandatory Palestine"](http://web.nli.org.il/sites/nlis/en/jrayed), the [Moise A. Khayrallah Center for Lebanese Diaspora Studies](https://lebanesestudies.omeka.chass.ncsu.edu/collections/browse) or the [Institut du Monde Arabe](http://ima.bibalex.org/IMA/presentation/home/list.jsf)
[^2]: such as [*Arshīf al-majallāt al-adabiyya wa-l-thaqāfiyya al-ʿarabiyya*](http://archive.sakhrit.co) or [*al-Maktaba al-Shāmila*](http://www.shamela.ws/), [*Mishkāt*](http://almeshkat.net/), [*Ṣayyid al-Fawāʾid*](http://saaid.net/) or [*al-Waraq*](http://www.alwaraq.net/)

[^3]: It must be noted that the US-based HathiTrust does not provide public or open access to its collections even to material deemed in the public domain under extremely strict US copyright laws when users try to connect to the collection from outside the USA. On the issue of unequal access to digitised collections see {Gooding 2018@145-170} and especially his Figure 6.1 showing global access (or lack thereof) to the British Library Nineteenth Century Newspapers. {--Citing the absence of editors able to read many of the languages written in non-Latin scripts, HathiTrust tends to be extra cautious with the material of interest to us and restricts access by default to US-IPs. These restrictions can be lifted on a case-by-case basis, which requires at least an English email conversation and prevents access to the collection for many of the communities who produced these cultural artefacts; see [https://www.hathitrust.org/access_use](https://www.hathitrust.org/access_use) for the access policies.--}

[^18]: {website_eapb}

[^19]: For good overviews on the issue of digital (scholarly) editions see {Driscoll 2016;Pierazzo 2015;Sahle 2013}.

<!-- If the "data" is lacking, can we use (bibliographic) metadata? -->

In the absence of *digital* editions, any meaningful computational analysis of the  connections between authors, texts, and periodicals as a venue for publication and review requires access to reliable standardised bibliographic metadata as a bare minimum. Unfortunately, even this data is practically non-existent. This is due to ambiguity and incorrect data found in the original artefact; to lacking familiarity with the particularities of these artefacts among cataloguers, librarians and scholars; and to a software stack ill-suited for anything but Western concepts of dates and names and Western scripts. 

<!-- faulty publication data as provided by the periodicals themselves; a) dates, b) names -->

Periodicals seem to provide no dating challenges since publication dates were conveniently recorded in a masthead. However, periodicals across the Arabic speaking late Ottoman Eastern Mediterranean made use of at least four calendars. Newspapers and journals provided dates in any combination of the Ottoman fiscal, or *mālī* calendar and the reformed Julian calendar as well as the better known Islamic *hijri* and Gregorian calendars. In addition to at least three different year counts, these calendars and their users also differed in their conception of the calendric day. Most retained the old notion of a day commencing at sundown, while others adopted *alla franca* time with 24 equinoctial hours and a date change at midnight.[^35] Unfortunately supplied dates from mastheads frequently neither matched each other nor the day of the week the paper was supposedly printed on. {==A particularly illuminating example in our corpus can be found in the masthead to issue 6 of the Damascene journal *al-Ḥaqāʾiq* that read "First of the holy month of *Muḥarram* 1229 [*hijrī*], 3 *Kānūn Awwal* 1327 [*mālī*], and 20 December (*Kānūn Awwal*) of the year 1911 [Gregorian]".[^23] This line contains at least four errors: First the *hijrī* date is set in the wrong century and should read 1329. Second, the days of the *mālī* and Gregorian dates got mixed up. The Gregorian calendar was thirteen days ahead of Julian calendars since the year 1900. The corrected *mālī* date should read 20 *Kānūn Awwal* instead of the third, but because the *mālī* years began in spring with the month of *mārt* (March), the year count should not have been incremented to 1327 with the beginning of the new *hijrī* year. Therefore the correct *mālī* date would have been "20 *Kānūn Awwal* 1326".  The Gregorian date, finally, is even wrong after fixing the mix-up of days with the *mālī* date. Instead of *Kānūn Awwal* (December) it should be *Kānūn Thānī* (January) and since December has 31 days, the correct Gregorian date should ultimately read "2 {--(instead of the substituted 3 from the original, faulty, *mālī* date)--} January 1911".==}{>>delete?!<<} How should one record this bibliographic nightmare? And which date-calendar combination should be considered the authoritative one? What if recorded publication dates were fictional to simulate a regular publication cycle and should therefore be conceived of as issue numbers that have only limited relation to an actual date?[^24] 

[^23]: *al-Haqāʾiq* 1(6), available online at <https://openarabicpe.github.io/digital-haqaiq/xml/oclc_644997575-i_6.TEIP5.xml>. Note that digital facsimiles are geo-fenced and only accessible to US IPs.

[^24]: *al-Muqtabas*, for instance, was severely lagging behind its publication schedule by summer 1909. [No. 4(7)](https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_42.TEIP5.xml) was scheduled for Rajab 1327 aH (July/August 1909) according to its masthead, but only published in the first week of April the following year; see {muqtabas 76-eap@3}. *al-Ḥaqāʾiq* is more difficult to date through external source because unlike *al-Muqtabas* it was only rarely mentioned in other publications. However, a prolonged dispute with the newspaper *al-Muqtabas* in 1911 provides some clues. {haqaiq i:12@476} referenced {muqtabas 288-eap}. Therefore, it must have been published at least 10 days after the publication date provided by the masthead. {>>*al-Ḥaqāʾiq* 1(6) referenced an article in *al-Muqtabas* 1 December 1910 (#539)<<}

<!-- 2) lack of knowledge among cataloguers -->

Any attempt to answer these questions relies on the affordances of available information systems, that is people and their skills, abstract concepts, and actual tools to record and retrieve these data points. But cataloguers, librarians and even specialists of the late Ottoman Eastern Mediterranean are frequently unfamiliar with calendric systems beyond the solar Gregorian and the Islamic lunar *hijrī* calendars. *Mālī* years are frequently misread as *hijrī* years, which introduces a margin of error of up to two years for the last decades before World War I.[^25] <!-- 3) short-comings of the software --> Second, most software is unable to work with anything but Gregorian dates out of the box.  Even if cataloguers were able to correctly establish the calendar used in a periodical's masthead, the computing infrastructure would not allow them to enter this date into the digital record.[^20]
Finally, even when bibliographic data is internally kept in structured  form, it is not commonly shared in a standard-compliant and machine-actionable format{--, such as MARC or MODS--}.[^21] A good example for this state of affairs is the British Library's otherwise excellent Endangered Archives Programme (EAP), which digitised periodical holdings of the al-Aqsa Mosque's library in Jerusalem. If we look at the [fourth volume](https://eap.bl.uk/archive-file/EAP119-1-4-3) of the journal *al-Muqtabas* available through EAP, we find that bibliographic information is solely provided in unstructured plain text{-- either through the web interface or the IIIF API--}.[^22] Publication dates are provided as Gregorian months even though the cover clearly states that *al-Muqtabas* follows the "Arabic", i.e. Islamic *hijrī*, calendar and despite each issue reporting the publication date as *hijrī* month. Consequently, there is a dissonance between the facsimile and the bibliographic information. *al-Muqtabas* 4(1) recorded the month of *Muḥarram* 1327 aH in its masthead. Depending on the local observation of the moon in Damascus, the journal's place of publication, this month began around 27 January 1909. Should *al-Muqtabas* 4(1) therefore be considered the January or the February  issue? The cataloguers at EAP clearly thought the latter or their cataloguing software did not allow for date ranges.

[^25]: Stefan Weber and Jens Hanssen, for instance, missed the fact that the birthday of Sultan ʿAbdülḥamīd II (1876--1909) was celebrated according to the Islamic *hijrī* calendar and thus rotated through the solar year. The annual celebrations of the anniversary of the ʿAbdülḥamīd II's accession to the throne were celebrated according to the empire's *mālī* calendar. Yet, leading scholars read these dates as pertaining to the *hijrī* calendar. Due to the mix-up in 1872 and the resulting growing difference between the two calendars, ʿAbdülḥamīd II's silver jubilee on the throne is wrongly dated to 1901 instead of 1900. {Hanssen 2005@238, 243ff.; Weber 2009@418-420;Deringil 1998@29; Uluengin 2010@20}.

[^35]: The Islamic *hijrī* calendar is a lunar calendar beginning the year with 1 *Muḥarram* and counting years since the prophet Muḥammad's flight (*hijra*) from Mecca to Medina in 622. Dates differ between locations as the beginning of the month is based on sightings of the new moon. They cannot, therefore, be reliably computed. A common workaround without recourse to empirical observations as provided in large tabular publications is to compute the astronomic lunar calendar instead. The reformed Julian calendar is a solar calendar beginning the year with 1 January. Every one hundred years the difference between the Gregorian and Julian calendar increases by one day due to different rules for adding an intercalated 366th day every four years. In the Ottoman context, the reformed Julian calendar is commonly referred to as *rūmī*. Arabic periodicals usually labelled this calendar as *sharqī* (Eastern). The Ottoman fiscal *mālī* calendar is a lunosolar calendar. It is based on the Old Julian calendar beginning the year with 1 March and was designed to synchronise the year count with the *hijrī* calendar. Introduced in 1676 it is also sometimes confusingly called *rūmī*. Due to a printing error in the coupon booklets for the Ottoman consolidated debt repayment program for 1872, synchronisation of *mālī* and *hijrī* years was henceforth abolished. {>>some references needed<<} {Jajko 1993;Rose 1991;Deny 1921;Georgeon 2011}.

[^20]: Consider, for instance, the quasi standard for digital scholarly editions, TEI, which is expressed in XML. According to the XPath specifications, the [`format-date()`](https://www.w3.org/TR/xpath-functions-30/#func-format-date) function supports a number calendars beyond the Gregorian standard, including the Islamic *hijrī* calendar, since version 2.0. However, the actual support for calendars and languages is implementation-dependent and Saxon, the main XSLT, XPath and XQuery processor, has not implemented any of these alternative calendars; see [documentation for `format-dateTime()`](https://www.saxonica.com/html/documentation/functions/fn/format-dateTime.html).

[^21]: Such as [MAchine-Readable Cataloging (MARC)](http://www.loc.gov/marc/) and [Metadata Object Description Schema (MODS)](http://www.loc.gov/standards/mods/) standards. Both are maintained by the [Network Development and MARC Standards Office of the Library of Congress (NDMSO)](http://www.loc.gov/marc/ndmso.html). MARC can be serialised as XML but frequently isn't. MODS, in contrast, is expressed in XML and more human-readable.

[^22]: This is true for the web interface and the [IIIF (International Image Interoperability Framework)](https://iiif.io) API. <https://eap.bl.uk/archive-file/EAP119-1-4-3>. As part of OpenArabicPE, *al-Muqtabas* 4(1) is available at <https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_37.TEIP5.xml>.

Even if we had perfectly reliable digital re-mediations of the bibliographic information found in the periodical issues themselves, the vast majority of articles would remain outside our analytical scopes because publishers did not provide (meaningful) bylines---most articles in  journals and newspapers from Baghdad, Beirut, Cairo or Damascus did not credit their authors. One approach would be to subject all articles to stylometric analysis for authorship attribution (more on this below) but this again presupposes truly *digital* editions.

<!-- identify the areas to catch up with -->

Note that a the full text of a periodical is necessary but not sufficient for many analytical queries and distant reading. It is certainly insufficient for close reading. The full text of a periodical would be nothing but a string of words. But periodicals unite different texts of various genres from multiple authors. These texts are commonly grouped into issues and volumes and longer ones were frequently serialised and scattered across issues. Some of these texts will be reprints from other periodicals or first printed publications of much older manuscripts. Some of the texts are responses, etc. In order to make sense of the full text of a periodical for both humans and machines it has to be modelled.

<!-- get the full text -->

Optical character recognition (OCR), the technology to convert an image into machine-readable text, has come a long way and even hand-written text recognition (HTR) is fairly successful at least for Latin script.[^9] Automatic recognition of Arabic script, however, is severely lacking behind for a variety of reasons beyond the scope of this paper.[^4] Despite promising developments with the application of machine-learning technologies to pattern recognition,[^7] automatic conversion of images of early Arabic periodicals is hampered by three factors: first, all OCR technologies depend on  training sets of "gold standard" transcriptions as ground truth; second, low-quality fonts, inks, and paper employed at the turn of the twentieth century will inevitably result in poor print quality; and third, text recognition depends on layout recognition and multi-column texts with various intersections of boilerplate, ads, etc. pose serious challenges. Consequently these texts can currently only be reliably digitised by human transcription.[^12] Funds for transcribing the tens to hundreds of thousands of pages of an average mundane periodical are simply not available, despite of their cultural significance and unlike for valuable manuscripts and high-brow literature.

[^12]: The validity of this statement, of course, depends on the purpose of digitisation. If one was, for instance, interested in distant reading approaches to large corpora, such as the temporal distribution of certain keywords during a long print run, this would allow not just for aggregation on the issue level but probably even periods of full months and more. In consequence, error margins of almost one fourth in both Character Error Rate (CER) and Word Error Rate (WER) become seemingly acceptable; e.g. {Cristianini 2018@144}. Ryan Cordell argues for the importance of theorising the impact of OCR on scholarly findings. Cordell poses that OCR must be considered a new edition subject to "elaborate systems of scholarship, preservation, bureaucracy, human labor, machine processes, and economics"; {Cordell 2017@188}.

[^4]: C.f. {Märgner 2012a}. For recent promising approaches using machine-learning and neural networks see {Romanov_2016}. For examples of the state of Arabic OCR even for well-funded corporations and projects, try searching inside Arabic works on Google Books or HathiTrust. The ["Early Arabic Printed Books" (EAPB) project](http://gale.cengage.co.uk/arabic), currently under development by GALE in collaboration with the British Library, makes repeated claims of employing "newly developed optical character recognition software (OCR) for early Arabic printed script" (see this [factsheet](http://gale.cengage.co.uk/images/EAPB-Factsheet_English_WEB.pdf)). But since they share neither text layers nor error rates or software, their claims cannot be verified. As a substantial number of the digitised books in EAPB are written in languages other than Arabic that employ Arabic script (such as Farsī, Urdu or Ottoman Turkish) and as some works resemble complex manuscripts with multiple commentaries around a main text fully automated text-retrieval is highly unlikely.

[^7]: The [Open Islamicate Text Initiative (OpenITI)](http://iti-corpus.github.io/) project planned to publish its tool chain in 2018. For an overview of their work see <http://islamichistorycommons.org/mem/wp-content/uploads/sites/55/2017/11/UW-25-Savant-et-al.pdf>.

[^9]: One major research project for HTR is [Transkribus](https://transkribus.eu/Transkribus/). Sinai Rusinek and I have begun experimenting with submitting OpenArabicPE's editions as ground truth for training Transkribus. First results for single-column Arabic periodicals are promising and report a CER of less than 10 per cent, which would be sufficient for some distant reading applications.

Grey online-libraries of Arabic literature, namely [*al-Maktaba al-Shamila* (*shamela.ws*)][shamela], [*Mishkat*][almeshkat], [*Saydal-Fawa'id*][saaid] or [*al-Waraq*][alwaraq], provide access to a vast body of (mostly classical) Arabic texts including transcriptions of unknown provenance, editorial principals, and quality for a small number periodicals. These grey "editions" lack information linking the digital representation to material originals, namely bibliographic metadata and page breaks, which makes them almost impossible to employ for scholarly research.

Since we do not have the resources to proof and correct these texts, we had the idea to build our own corpus by uniting transcriptions from grey online libraries with the digital facsimiles from other sources as a means to verify the quality of the digital text. Thus "Open Arabic Periodical Editions" (OpenArabicPE) was born in autumn 2015. {>>comment on the arbitrary composition of this corpus<<}

# Building a corpus of *digital* Arabic periodicals

[OpenArabicPE](https://openarabicpe.github.io) establishes a framework for open, collaborative, and fully-referencable scholarly digital editions of early Arabic periodicals. The guiding principles of OpenArabicPE can be summarised as *accessibility*, *sustainability*, *credibility*. Starting with the mostly Damascene periodicals *al-Muqtabas* and *al-Ḥaqāʾiq*, OpenArabicPE demonstrates that one can produce scholarly editions that offer solutions for most of the above-mentioned problems---including the absence of expensive infrastructure---through re-purposing well-established open software platforms and by combining the virtues of immensely popular, but non-academic (and, at least under US copyright laws, occasionally illegal) online libraries of volunteers on the one hand with academic scanning efforts as well as editorial expertise on the other.

Within OpenArabicPE we devise workflows and tools to transform digital texts from [*shamela.ws*][shamela] into an open, standardised file format (XML) following the [Text Encoding Initiative (TEI)](https://www.tei-c.org)'s guidelines,[^8] to generate bibliographic metadata, and to render a parallel display of text and facsimile in a web browser. We add light structural mark-up for articles, sections, authors, and bibliographic metadata, and link each page to facsimiles from various sources, namely [EAP][bl], [HathiTrust][hathitrust], and [archive.sakhrit.co][sakhrit].[^36] The latter step, in the process of which we also make first corrections to the transcription, though trivial, is the most labour-intensive because page breaks were commonly ignored by *shamela.ws*'s anonymous transcribers. This point needs to be emphasised: each of the c.8500 pages breaks in *al-Muqtabas* and *al-Ḥaqāʾiq* needed to be manually marked by volunteers in order to link facsimiles to the digital text and thus make the text verifiable for human readers.[^6] So far Dimitar Dragnev, Talha Güzel, Dilan Hatun, Hans Magne Jaatun, Xaver Kretzschmar, Daniel Lloyd, Klara Mayer, Tobias Sick, Manzi Tanna-Händel and Layla Youssef have contributed their time to this task.

[^6]: In other instances, such as the journals [*Lughat al-ʿArab*](https://github.com/OpenArabicPE/journal_lughat-al-arab), [*al-Ustādh*](https://github.com/OpenArabicPE/journal_al-ustadh)  or [Yūsuf Ilyān Sarkīs' *Muʿjam al-maṭbūʿat al-ʿarabiyya wa-l-muʿarraba* (Miṣr: Maṭbaʿat Sarkīs, 1928)](http://shamela.ws/index.php/book/1242), *shamela.ws* did provide page breaks that correspond to a printed edition.

[^8]: TEI XML is the quasi-standard of textual editing and required by funding bodies and repositories for long-term archiving; cf. {DfgPraxisregelnDigitalisierung 2016}.

[^36]: Note that archive.sakhrit.co has since moved to [http://archive.alsharekh.org/](http://archive.alsharekh.org/)

All tools and the editions are hosted on the code-sharing platform [GitHub](https://www.github.com) under MIT and Creative Commons [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/) licenses for reading, contribution, and re-use.[^10] {>>mention collaboration with Leipzig and the integration of Muqtabas into CLARIN<<} As part of the editions we provide structured bibliographic metadata for every article  in machine-readable format that can easily be integrated into larger bibliographic information systems.[^26]

[^10]: We claim that text of all periodicals in our corpus and originally published before 1920 is in the public domain even under the most restrictive definitions (i.e. in the USA); the anonymous original transcribers at *shamela.ws* do not claim copyright; and we only link to publicly accessible facsimile's without copying or downloading them. All code is archived on the Open Science platform [Zenodo](https://www.zenodo.org) that also provides stable identifiers (DOI) for every release.
[^26]: In addition, we make this data accessible through a constantly updated public [Zotero group](https://www.zotero.org/groups/OpenArabicPE).

With OpenArabicPE we argue that by linking facsimiles to the digital text, every reader can validate the quality of the transcription against the original. We thus remove the greatest limitation of crowd-sourced or grey transcriptions and the main source of disciplinary contempt among historians and scholars of the Middle East. Improvements of the transcription and mark-up can be crowd-sourced with clear attribution of authorship and version control using .git and GitHub's core functionality. Such an approach as proposed by Christian Wittern[^27] has recently seen a number of concurrent practical implementations such as project [GITenberg](https://gitenberg.github.io/) led by Seth Woodworth or Jonathan Reeve's [Git-lit](https://github.com/Git-Lit/git-lit).

[^27]: {Wittern 2013}

## OpenArabicPE's corpus

The corpus comprises the full text of each issue of *Lughat al-ʿArab*, *al-Muqtabas* and *al-Ḥaqāʾiq* and a transcription of article titles and bylines for one volume of *al-Ḥasnāʾ* until the end of World War I. <!-- This comes down to a total of 165 periodical issues with some 2.65 million words. -->

| journal             | volumes   | issues   | articles   | independent articles   | articles with author   | in %     | words      | words.per.article   | characters.per.word   |
| ------------------- | --------- | -------- | ---------- | ---------------------- | ---------------------- | -------: | --------: | ------------------- | --------------------- |
| *al-Ḥaqāʾiq*        | 3         | 35       | 389        | 257                    | 163                    | 41.90    | 298090     | 832.660484848951    | 4.42336130476421      |
| *al-Ḥasnāʾ*         | 1         | 11       | 173        | 136                    | 63                     | 36.42    |            |                     | 4.29100836427165      |
| *al-Muqtabas*       | 9         | 96       | 2964       | 792                    | 377                    | 12.72    | 1981081    | 873.341307920755    | 4.51753515150654      |
| *Lughat al-ʿArab*   | 3         | 34       | 939        | 330                    | 152                    | 16.18    | 373832     | 485.206043680748    | 4.39265321063476      |
| **total**           | 16        | 176      | 4465       | 1515                   | 755                    |          | 2653003    |                     |                       |

Table: summary of our corpus

<!-- ### *al-Muqtabas* -->

Muḥammad Kurd ʿAlī (1876–1953) was the best known and, after the Young Turk Revolution of 1908, the most influential journalist and intellectual in Damascus. Before establishing his journal *al-Muqtabas* (The Digest) in Cairo in 1906 and the first daily newspaper to be published in Damascus in 1908 (also confusingly called *al-Muqtabas*), he had held minor government offices and worked at various public and private presses and periodicals in Damascus and Cairo. He was well-acquainted with leading figures of the Islamic reform movement in Egypt and Greater Syria. He was a member in Ṭāhir al-Jazāʾirī's "senior circle" in the early 1890s in Damascus and later moved and worked in Rashīd Riḍā's and Muḥammad ʿAbduh's circles in Cairo. After the Young Turk Revolution, Kurd ʿAlī returned to his hometown and the publication of *al-Muqtabas* moved from Cairo to Damascus in the journal's third year. In Damascus, *al-Muqtabas* soon became "the boldest, most coherent, consistent and committed proponent of reform and modernity [...] prior to World War I".[^33] Due to conflicts with the authorities over the reprint of a poem, Kurd ʿAlī again fled Damascus for Cairo and Europe in 1912. Consequently, *al-Muqtabas* was published from Cairo for a couple of months before Kurd ʿAlī was allowed to return once again. During World War I and Cemal Pasha's infamous term as commander-in-chief of the 4th Army and governor general of Syria, Kurd ʿAlī was able to win his support. He thus escaped the fate of Shukrī al-ʿAsalī{>> his co-editor at *al-Muqtabas*<<}, ʿAbd al-Ghanī al-ʿUraysī and other journalists from Beirut and Damascus, who were publicly executed on charges of treason. Similarly to their editor, the journal and the newspaper *al-Muqtabas* survived and continued publication until the final days of the war---albeit in shorter and less frequent editions due to material shortages. After the end of the war and the disintegration of the Ottoman Empire, Kurd ʿAlī abandoned the monthly and left the editorship of the revived daily newspaper *al-Muqtabas* to his brother Aḥmad. He founded the Arab Scientific Academy whose president he became in 1919 and served twice as Minister of Education (1920–22, 1928–32) during the French Mandate over Syria.[^34]
The edition of *al-Muqtabas* gathers all 96 issues published between 1906 and 1917/18 with a total of some 7.000 pages and almost 2 million words. {>>comment on print runs<<} Issues consist of longer independent articles and sections with shorter articles such as brief reports on new discoveries and book announcements. Issues and pages differed widely in length. On average, each issue contained 65 pages with almost 300 words or 20354 word per issue.

[^33]: {Seikaly 1981@128}

[^34]: For an autobiographic sketch see {KurdʿAlī 1928@411-425}. For intellectual biographies see {Seikaly 1981; Hermann 1990}.

<!-- ### *al-Ḥaqāʾiq* -->

Much less is known about the second Damascene journal in our corpus and the people behind it. The *ʿālim* (religious scholar) ʿAbd al-Qādir al-Iskandarānī (1875--1943) came from the notable al-Kaylānī family, who were closely associated with the Qadriyya Sufi order. He published three volumes with a total of 35 issues of *al-Ḥaqāʾiq* (The Facts) in Damascus between 1910 and 1913. *al-Ḥaqāʾiq* was a periodical of the conservative Muslim establishment, who called themselves *mutayyinūn* (the very pious). The journal had a strong focus on Islamic topics and published constant critiques of Salafism and "Westernised" journals, such as *al-Muqtabas*.[^37] Its page layout conveys an apparent lack of familiarity with the by then established conventions of Arabic journals, which further underlines its nature as an outlier in the ideosphere of Arabic periodicals. Unlike Kurd ʿAlī, al-Iskandarānī did not claim a single byline in "his" journal or any other periodical in our corpus.
Pages contain much less text and issues are much shorter than *al-Muqtabas* with a total of 300186 words across 1436 pages (as some 17 pages are missing from the transcription, the word count is too low). Save for a double issue, the vast majority of issues (28 of 36) comprised 40 pages with an average of slightly more than 200 words each. This results in an average 8516 words per issue compared to the 20636 words of *al-Muqtabas*.

[^37]: For controversies between *al-Muqtabas* and *al-Haqāʾiq* see {Gelvin 2012; Commins 1990@118-122}.

<!-- ### *Lughat al-ʿArab* -->

The Carmelite Father Anastās Mārī al-Karmalī (born Buṭrus ʿAwwād, 1866--1947) from Mt. Lebanon established the monthly journal *lughat al-ʿArab* (The Language of the Arabs) in Baghdad in 1911. The journal published 34 issues until its final number in June 1914<!--  (it was re-established in  -->. al-Karmalī was exiled to Kayseri in Anatolia upon the beginning of WWI and returned in summer 1916. *Lughat al-ʿArab* recommenced publication only in 1926.[^44] It is not clear to which extent al-Karmalī was involved as editor. Only a (small) handful of articles in *lughat al-ʿArab* carried his byline. Kāẓim al-Dujaylī (1884--1970), a self-taught journalist and poet and student of the Baghdadi Salafist Shukrī al-Alūsī and al-Karmalī, joined *Lughat al-ʿArab* as editor(-in-chief?) soon after. 
Similar to *al-Ḥaqā'iq*, issues comprised mostly 40 pages with an average of almost 240 words per page and a total of 11274 words. {>>Basic information from {RizkKhoury 2010@335}<<}

[^44]: *Lughat al-ʿArab* 4(1):1, {JournalOfTheAmerican 1920}.

# Network of authors and texts

With major work on modelling on three journals from Baghdad, Cairo and Damascus---*Lughat al-ʿArab*, *al-Muqtabas* and *al-Ḥaqāʾiq*---done, we can now begin to submit this corpus to initial analyses of the social and geographic networks of authors and their texts as well as the network of periodicals referenced and cited in these three journals.

<!-- state of the data -->

The quality and significance of the analysis of bibliographic data is directly dependent on the quality of the information provided by the periodicals themselves and of our mark-up in the digital editions. All relevant personal and place names in bylines and other source information must be marked up for retrieval. A core step is the necessary disambiguation of named entities through local and external authority files: "Anastās al-Karmalī", "Buṭrus ʿAwwad", "Sātisnā" and "The publisher of *Lughat al-ʿArab*", for example, refer to the same person, "*Ḥalab*" and "*al-Shahbāʾ*" both designated the city of Aleppo. By linking references to external authority files and the semantic web, we can harvest additional information on authors and locations, namely the geolocation for toponyms, transcriptions into Latin script necessary for working with most visualisation tools, and life dates for persons in order to establish the age of authors upon publication.{>>Comment on the issue of many visualisation tools, such as R and Gephi for macOS, not working with Arabic script<<}It must be noted that, as in any other step along the process of this research project, scholars of non-Western societies are at a significant disadvantage. Automated named-entity recognition (NER) is well established for western languages but there are is currently no readily available software that supports Arabic.[^57] Openly available authority files, such as the [Virtual International Authority File (VIAF)](https://viaf.org) that aggregates tens of national authority files and which, in turn, depend on expensive infrastructures and are subject to the same digital affordances alluded to above (English interface, names as combinations of fore- and surnames, Gregorian calendar). As a result, they are heavily biased towards the Global North.[^48]

[^57]: The standard open-source NER tool, the [Stanford Named Entity Recognizer](https://nlp.stanford.edu/software/CRF-NER.html), does not support NER for Arabic. 

[^48]: contributing institutions and libraries are listed on the homepage [http://viaf.org](http://viaf.org).

## Evaluating the corpus: network of referenced periodicals

Knowing that we work with a corpus whose composition is the result of external and unknown decisions by the contributors to *al-Maktaba al-Shamela* as to which periodical to transcribe, we can evaluate the performance of this corpus in representing the larger ideosphere of the periodical press in the late Ottoman Eastern Mediterranean by looking at the network of referenced periodicals. Explicit references to periodicals indicated by "*jarīda* XYZ" or "*majalla* ABC" were automatically marked-up using XSLT and regular expressions and linked to local and external authority files for disambiguation and additional bibliographic information. We then counted the references to each mentioned periodical and plotted the result as a network graph. We plotted networks of references by issue to account for the varying length of articles in each journal.{>>sequencing into even-sized chunks might be a good idea for statistical validity<<} In the network plots below each node signifies a periodical (newspapers and journals are not distinguished at the moment). Edges are drawn between periodical titles when one references the other. The thickness of the edges and the size of the nodes indicate the number of issues that reference a periodical (weight). Colours signify the {==in-degree==}{>>i.e. the number of edges that connect to a node;<<} or the number of journals in our corpus that mention this periodical (3 = orange, 2 = green, 1 = purple).

<!-- ![Figure: Network of periodicals mentioned in *al-Haqāʾiq*, *al-Muqtabas* and *Lughat al-ʿArab*](assets/plots/network_oape-referenced-periodicals.png) -->

<!-- ![Figure: Network of periodicals mentioned *al-Ḥaqāʾiq*, *al-Ḥasnāʾ*, *Lughat al-ʿArab* and *al-Muqtabas*; weights per issue](assets/plots/network_oape-p3a6afa20_referenced-periodicals-per-issue.png) -->

![Figure: Network of periodicals mentioned *al-Ḥaqāʾiq*, *al-Ḥasnāʾ*, *Lughat al-ʿArab* and *al-Muqtabas*; weights per issue](assets/plots/network_oape-p3a6afa20_referenced-periodicals-per-issue_ar.png)

<!-- ![Figure: Core nodes in the network of periodicals mentioned *al-Ḥaqāʾiq*, *al-Ḥasnāʾ*, *Lughat al-ʿArab* and *al-Muqtabas*; weights per issue](assets/plots/network_oape-p3a6afa20_referenced-periodicals-per-issue-core.png) -->

![Figure: Core nodes in the network of periodicals mentioned *al-Ḥaqāʾiq*, *al-Ḥasnāʾ*, *Lughat al-ʿArab* and *al-Muqtabas*; weights per issue](assets/plots/network_oape-p3a6afa20_referenced-periodicals-per-issue-core_ar.png)

The first observation, common to all social networks, is that only a very small number of nodes are of relative importance, as measured in in-degree (number of edges connecting to a node) and weight of the edges connecting nodes. Out of a total of 465 different periodical titles, 421 or c. 90% were referred to by only a single journal. 344 periodicals are only mentioned in a single issue and 335 in a single article. The second figure shows the 44 core nodes---periodicals that were referenced in more than one journal---in more detail. Only 9 (2,13%) were referenced by three journals in our corpus. {==They are: *al-Manār*, *al-Muqtaṭaf*, *al-Hilāl* and *al-Ḍiyā* from Cairo, *al-Muqtabas* itself, *al-Mufīd*, *al-Waṭan* and *al-Ḥaqīqa* from Beirut and *al-Ḥuqūq* from Mt. Lebanon ==}{>>comment: this fits the standard narrative of important journals, with the exception of *al-Mufīd* <<} The centrality of the {==three==} Cairene periodicals, *al-Manār*, *al-Muqtaṭaf*, *al-Hilāl*, which were all published by Syrian immigrants, tentatively confirms the standard narratives of the Arabic press.[^54] If we had the means to construct our own corpus without the severe limitations alluded to above, these would be the journals to digitise. Second, this network is highly centralised in terms of geographic distribution. The 44 core nodes were published in only a handful of locations: Beirut (9), Cairo (7), Baghdad, Damascus, Paris (3), Alexandria,  London, Mt. Lebanon, Saida and Zahle (1).{>>plot this information on a map?<<}{>>how many at which locations?<<}

<!-- *al-Ḍiyāʾ* was published by Ibrāhīm al-Yāzijī between 1898 and 1906, i.e. before the issues in our corpus. References are mainly in the form of "the publisher of *al-Ḍiyāʾ" -->
<!-- al-Mufīd was published by ʿAbd al-Ghanī al-ʿUraysī -->
<!-- neither *al-Ḍiyāʾ*, *al-Mufīd*, *al-Waṭan* nor *al-Ḥaqīqa* or *al-Ḥuqūq* feature prominently in Ayalon's work -->

[^54]: C.f. {Ayalon 1995@53-55}.

A third observation of the larger network is that *al-Muqtabas* accounts for the vast majority of references to other periodicals by some orders of magnitude even after we account for *al-Muqtabas* having almost thrice as many issues as either *al-Ḥaqāʾiq* or *Lughat al-ʿArab*. {==If we assume that we haven't missed a significant number of references==}{>>since mark-up was done automatically, this seems unlikely<<}, then *al-Muqtabas* was more outward-looking and more involved in larger discourses of the day. Fourth, a closer look at the core nodes in the network reveals that all periodicals were primarily self-referential---indicated by the thickest edges connecting a journal to itself (for the purpose of this visualisation and to prevent circular edges, source and target nodes were separated). Fifth, the core nodes include number of surprises: *al-Jinān* was published by Butrus al-Bustānī and later his son Salīm al-Bustānī in Beirut between 1876 and 1886. This means that either *al-Jinān* was still relevant for certain discourses long after it ceased publication or that the corpus, spanning the years 1906 until 1918, contains a number of historiographic texts mentioning important journals of the past. Articles in Ibrāhīm al-Yazījī's *al-Ḍiyāʾ*, published in Cairo between 1898 and 1906, were equally referenced after the end of this periodical. Finally, the group of periodicals referenced in two journals in our corpus comprises a number of foreign titles such as  *Le Temps*, *Revue des Revues* and *Revue du Monde Musulman* from Paris and *The Times* from London (*alTan*, *mjl0 almjlat*, *altyms* in the plots).

{>>what are the lacunae in this network? which periodicals are not referenced?<<}

## analysis of metadata: network of authors

Sketching a network of periodicals and the references between them is only one part in the endeavour to layout the ideosphere of the late Ottoman Eastern Mediterranean. Another is the network of authors who published in these periodicals and the geographic distribution of places mentioned in bylines. {>>Other layers of this ideosphere not covered in this short overview but worth exploring are the network of works reviewed and mentioned in our corpus. What was read and written about in Damascus and Baghdad?<<} Knowing the importance of certain authors for an individual periodical is the basis for mapping the {>>social<<} network of authors across the late Ottoman ideosphere.{>>these findings would need to be contextualised by traditional intellectual history<<} The aim would be to map such a network for the hundreds of journals and newspapers published between Alexandria and Aleppo, Jaffa and Basra. Nevertheless, this method already provides valuable insights using our small corpus of bibliographic metadata:

![Figure: Network of authors with bylines in *al-Ḥaqāʾiq*, *al-Ḥasnāʾ*, *Lughat al-ʿArab* and *al-Muqtabas*](assets/plots/network_oape-p3a6afa20_authors_unimodal_ar.png)

It is worth going back to the bibliographic {>>meta<<}data, its shortcomings and the resulting consequences for our analysis before looking at this aggregated information. We are particularly concerned with the number of articles that carried bylines or otherwise easily identifiable authorship information.[^55] All journals in our corpus, like any other periodical at the time I have seen, published only limited authorship information. In this regard *al-Ḥaqāʾiq* is the least offending. About 42 per cent of all articles (163 of 389) carried authorship information. Second is *al-Ḥasnāʾ* with 36 per cent (63 of 173), followed by *Lughat al-ʿArab* with 16 per cent (152 of 939) and *al-Muqtabas* with not even 13 per cent (377 of 2964). The picture becomes more favourable for the latter if we look only at longer articles. About two fifths of articles outside news and review sections explicitly mentioned an author. However, in consequence and due to the heavy weight of *al-Muqtabas*, this means that we can only map 16,91 per cent of the entire network of articles by looking at available bibliographic information alone. {==More than four fifths are hidden from our view.==} We can currently identify only a total of 319 named authors within this sample: 139 for *al-Muqtabas*, 103 for *al-Haqāʾiq*, 52 for *Lughat al-ʿArab*, and 42 for *al-Ḥasnāʾ*. Quite a significant number appear only with their initials, particularly in *al-Ḥaqāʾiq*, and---with the exception of *al-Ḥasnāʾ*---all of them were men. 

[^55]: In addition to intrinsic bibliographic information, such as bylines and footnotes, I also explicitly encoded extrinsic information on authorship. Muḥammad Kurd ʿAlī, for instance, is well known to be the author of a series of letters titled *Gharāʾib al-Gharb* (Oddities of the West). The gathering and encoding of extrinsic information cannot considered systematic or comprehensive at this point.

The first observation, similar the network of periodicals, is that only a very small number of nodes (14 of 319) are of relative importance as measured in degree (number of edges connecting to a node) and weight of the edges. In the above network plot, edges were drawn between authors when they published in the same periodical. The thickness of the edges and size of nodes are functions of the number of articles carrying the byline of a given author. Colours signify the out-degree or the number of journals an author is connected to. Authors who published only in a single journal form dense clusters{-- around that periodical's node--}. These are: *al-Ḥaqāʾiq* to the left, *al-Muqtabas* top centre, *Lughat al-ʿArab* bottom centre, and *al-Ḥasnāʾ* to the right.

![Figure: Core nodes in the network of authors with bylines in *al-Ḥaqāʾiq*, *al-Ḥasnāʾ*, *Lughat al-ʿArab* and *al-Muqtabas*](assets/plots/network_oape-p3a6afa20_authors-core_unimodal_ar.png)

If we look at the central nodes of the network more closely, we can observe that only one author published in all four journals: Maʿrūf al-Ruṣāfī was a famous poet from Baghdad who mostly authored *qaṣāʾid* on current political affairs. He moved to Istanbul after the Young Turk Revolution, where he worked as an Arabic teacher at the Royal College and at the newspaper *Sabīl al-Rashad*. He was elected MP for al-Muthanna (Iraq) in 1912 and 1914. After WWI he became a member of the Arab Scientific Academy, established by Muḥammad Kurd ʿAlī in Damascus.[^45] al-Ruṣāfī's close ties to *al-Muqtabas* and Kurd ʿAlī are further evident in the announcement in 1910 for the publication of a first collection of his poems, in which *al-Muqtabas* claimed that he was known among some people as "the poet of *al-Muqtabas*" and---wrongly---that "more than three quarters [of the *qaṣāʾid* therein] had been published in this journal".[^46] The publication of al-Ruṣāfī's *qaṣīda*'s in so many different periodicals---in addition to the journals in our corpus, I came across his *qaṣīda*'s in many other journals and newspapers---raises an important question regarding the production of newspapers: did he send his *qaṣīda*s to the editors of sometimes far away periodicals {==just like that==}{>>better wording<<}? Was he invited to contribute? Did editors take his texts from other sources?[^58] 

[^58]: E.g. {muqtabas 27-eap@1}{asr-2-203@3}, *al-ʿIrfān* 1(10):477--78, 1(12): 568-570, *al-Muqtaṭaf* 31(3):237--38. There is at least one case of an unacknowledged reprint: *al-tarbiyya wa-l-ummahāt* (Education and the mothers) was published in *al-Muqtabas* 4(1):34--36 (January 1909) and *al-Manār* 12(2):133-135 (March 1909), with the latter adding the comment that he sang it to himself in Beirut in Muḥarram 1327 aH (January - February 1909).

The other 13 central nodes had bylines in only two out of four journals. Only eight of the fourteen authors can be found in international authority files as aggregated in [VIAF (virtual international authority file)](http://viaf.org), which at least means that they have not authored works catalogued in any of the contributing libraries{-- (which, unsurprisingly, have a bias towards the Global North)--}.[^48] Those for whom we have biographic information (employing more traditional close reading of Arabic prosopographic literature)[^49] were on average in their mid-thirties during the years under investigation.
There is a {==surprising==}{>>why?<<} number of Iraqis and a notable absence of Syrians from this network of two Damascene journals and one periodical from Beirut and Baghdad each. Among the eleven identifiable authors, there are six Iraqis: Maʿrūf al-Ruṣāfī, Kāẓim al-Dujaylī, Ibrahīm Ḥilmī al-ʿAmr, Anastās Mārī al-Karmalī (often writing under the pen name Sātisnā), the two al-Shabībī brothers, Muḥammad Riḍā and Muḥammad Bāqir; three Egyptians: Muṣṭafā Ṣādiq al-Rāfiʿī, Aḥmad Muḥarram and Walī al-Dīn Yakan; and only two Syrians ʿĪsā Iskandar al-Maʿlūf and Muḥammad Rāghib Ṭabbākh. {==One would expect Syrians to figure much more prominently on account of the vast majority of articles being actually published in Damascus. In addition, Iraqis do not figure as prominently in the scholarly literature on the Arab renaissance (*nahḍa*). The religious composition of this core group raises the same issue: The ratio of two Christians among a group of 14 is a mirror of the larger populations but surprising if one considers the emphasis on Christians for the *nahḍa* in scholarly literature.==}{>>do I need this? Well there is an argument as to the dominance of Christian Arabs in the *nahḍa*<<}. It also important to note that Ami Ayalon, in his quasi standard account of the Arabic press, mentions only one of the fourteen, ʿĪsā Iskandar al-Maʿlūf and only in passing.[^59]

[^59]: {Ayalon 1995@53, 219}

In terms of education and occupations the core nodes are exemplary for the {==bourgeois middle-class intelligentsia of their time==}{>>add footnote on the loaded nature of these terms<<}: many attended Ottoman state schools in addition to more traditional, religious venues of education; many knew foreign languages in addition to Arabic and Ottoman; some were trained or even taught  abroad in the colonial centres of Paris and London; some served in the Ottoman bureaucracy; some were educators. There is also a significant number of poets (7) among the central nodes[^50] and a small number of politicians (MPs).{>>This is quite close to Muḥammad Kurd ʿAlī's description of the requirements for being a journalist (*ṣaḥāfī*). ({KurdʿAlī 1969a@86}) <<}
The more prolific of them were themselves journalists who at one time or another operated their own periodical(s): Maʿrūf al-Ruṣāfī, ʿIsā Iskandar al-Maʿlūf, Ibrāhīm Ḥilmī al-ʿAmr, Muḥammad Bāqir al-Shabībī, Kāẓim al-Dujaylī and  Anastās Mārī al-Karmalī, the publishers of *Lughat al-ʿArab*. Looking at the latter, the importance of *al-Muqtabas* in this small network (and beyond) cannot be overstated: al-Karmalī signed more articles in *al-Muqtabas* than his own journal *Lughat al-ʿArab*. The connection to Damascus and Muḥammad Kurd ʿAlī is further evident in four of the central nodes becoming members of the Arab Scientific Academy in Damascus after World War I, whose first president was Kurd ʿAlī himself.[^51]

Another striking observation is that despite two of the journals in our corpus, *al-Muqtabas* and *al-Ḥaqāʾiq*, were published in the same city, there is only very limited overlap. This contradicts the {==common==}{>>needs reference<<} assumption that due to the very small size of local journalistic circles---in 1912, five monthly journals were published in Damascus and none had a print run of more than a few hundred copies[^47]---there would be a substantial overlap in authorship.


[^45]: {Ziriklī 1979f@268-269}
[^46]: *al-Muqtabas* 4(10), p.620
[^47]: {Thomsen 1912@214}
[^49]: The most common prosopographic dictionaries for Arabic authors are {Ziriklī 1979;Kaḥḥāla 1957}.
[^50]: al-Ruṣāfī, al-Dujaylī, the two al-Shabībī brothers, al-Rāfiʿī, Muḥarram, Yakan
[^51]: al-Ruṣāfī, al-Dujaylī, al-Maʿlūf, Muḥammad Riḍā al-Shabībī.

| rank |                author.id.viaf                |      author.name      | author.name.transliterated | author.birth | author.death | journal.count | article.count | word.count |
|------|----------------------------------------------|-----------------------|----------------------------|--------------|--------------|---------------|---------------|------------|
|    1 | [14924300](https://viaf.org/viaf/14924300)   | معروف  الرصافي        | m3rwf  alrSafy             | 1875         | 1945         |             4 |            31 |      15038 |
|    2 | NA                                           | كاظم   الدجيلي        | kaZm   aldjyly             | 1884         | 1970         |             2 |            28 |      38050 |
|    3 | NA                                           | إبراهيم  حلمي  العمر  | abrahym  7lmy  al3mr       | 1890         | 1942         |             2 |            22 |      40747 |
|    4 | [40250618](https://viaf.org/viaf/40250618)   | عيسى  اسكندر  المعلوف | 3ysA  askndr  alm3lwf      | 1869         | 1956         |             2 |            22 |      23383 |
|    5 | [39370998](https://viaf.org/viaf/39370998)   | ساتسنا                | satsna                     | 1866         | 1947         |             2 |            15 |      20106 |
|    6 | [22006374](https://viaf.org/viaf/22006374)   | محمد  رضا  الشبيبي    | m7md  rDa  alWbyby         | 1889         | 1965         |             2 |            12 |      24156 |
|    7 | NA                                           | محمد  الهاشمي         | m7md  alhaWmy              | NA           | NA           |             2 |             6 |       2717 |
|    8 | [236524859](https://viaf.org/viaf/236524859) | مصطفى  صادق  الرافعي  | mSTfA  SadQ  alraf3y       | 1880         | 1937         |             2 |             6 |       3711 |
|    9 | NA                                           | محمد  باقر  الشبيبي   | m7md  baQr  alWbyby        | 1889         | 1960         |             2 |             5 |       3331 |
|   10 | NA                                           | أبو الضيا             | abw alDya                  | NA           | NA             |             2 |             4 |       5836 |
|   11 | [60500457](https://viaf.org/viaf/60500457)   | أحمد  محرم            | a7md  m7rm                 | 1877         | 1945         |             2 |             4 |       1543 |
|   12 | NA                                           | ا. ج                  | a. j                       | NA           | NA           |             2 |             3 |        639 |
|   13 | [63117968](https://viaf.org/viaf/63117968)   | محمد  راغب  طباخ      | m7md  raGb  TbaK           | 1877         | 1951         |             2 |             3 |       2633 |
|   14 | [36771043](https://viaf.org/viaf/36771043)   | ولي الدين   يكن       | wly aldyn   ykn            | 1873         | 1921         |             2 |             2 |        795 |

Table: authors that published in more than one journal in our corpus comprising *al-Ḥaqāʾiq*, *al-Ḥasnāʾ*, *Lughat al-ʿArab* and *al-Muqtabas*

### Individual periodicals

The work on compiling the biographies of all 319 contributors is far from being done, but after looking at the most productive authors for each journal, we can identify certain trends in the author populations and their geographic distributions.

<!--
|      journal      | number of authors | authors in VIAF | average year of birth |
|-------------------|-------------------|-----------------|-----------------------|
| *al-Ḥaqāʾiq*      |               103 |              15 |                  1837 |
| *al-Ḥasnāʾ*       |                42 |               6 |                  1883 |
| *Lughat al-ʿArab* |                52 |              12 |                  1875 |
| *al-Muqtabas*     |               139 |              65 |                  1869 |
-->

#### *al-Muqtabas*

Only 50 authors published more than one article in *al-Muqtabas*. Two of the four most prolific authors with more than ten bylines to their names wrote from Baghdad (See table below): Maʿrūf al-Ruṣāfī and Anastās Mārī al-Karmalī, using the pen name Sātisnā. ʿĪsā Iskandar al-Maʿlūf wrote mostly from Zaḥle and Yūsuf Jirjis Zakham from Omaha and Lincoln, Nebraska, USA. Only the fifth most prolific author was a native resident of Damascus: Muḥammad Kurd ʿAlī himself.[^60] {>>add comments on genre of texts by these authors<<}

[^60]: The article count for Muḥammad Kurd ʿAlī depends on the definition of an "article". If we count each section, originally published as letters in the newspaper *al-Muqtabas*, in his series *gharāʾib al-gharb* and *fī diyār al-gharb* as independent article, his article count would significantly spike.

<!-- The majority of the remaining authors contributed from the cities of Greater Syria and Egypt, but some wrote from cities in France. -->

| rank |                author.id.viaf                |     author.name     | author.birth | author.death | article.count |
|------|----------------------------------------------|---------------------|--------------|--------------|---------------|
|    1 | NA                                           | NA                  | NA           | NA           |          2630 |
|    2 | [14924300](https://viaf.org/viaf/14924300)   | معروف الرصافي       | 1875         | 1945         |            27 |
|    3 | [40250618](https://viaf.org/viaf/40250618)   | عيسى اسكندر المعلوف | 1869         | 1956         |            20 |
|    4 | [39370998](https://viaf.org/viaf/39370998)   | ساتسنا              | 1866         | 1947         |            14 |
|    5 | NA                                           | يوسف جرجس زخم       | 1880         | NA           |            13 |
|    6 | [32272677](https://viaf.org/viaf/32272677)   | محمد كرد علي        | 1876         | 1953         |            12 |
|    7 | [19737865](https://viaf.org/viaf/19737865)   | أحمد تيمور          | 1871         | 1930         |             9 |
|    8 | NA                                           | إبراهيم حلمي العمر  | 1890         | 1942         |             9 |
|    9 | [93607460](https://viaf.org/viaf/93607460)   | جمال الدين القاسمي  | 1866         | 1914         |             8 |
|   10 | [49218655](https://viaf.org/viaf/49218655)   | أحمد زكي            | 1866         | 1934         |             7 |
|   11 | [32410755](https://viaf.org/viaf/32410755)   | حافظ إبراهيم        | 1871         | 1932         |             7 |
|   12 | [28125663](https://viaf.org/viaf/28125663)   | رفيق العظم          | 1865         | 1925         |             7 |
|   13 | [118432135](https://viaf.org/viaf/118432135) | عبد القادر المغربي  | 1867         | 1956         |             7 |
|   14 | [22006374](https://viaf.org/viaf/22006374)   | محمد رضا الشبيبي    | 1889         | 1965         |             7 |
|   15 | [305214884](https://viaf.org/viaf/305214884) | جرجي حداد           | NA           | 1916         |             5 |


Table: The fifteen most prolific authors in *al-Muqtabas* by number of bylines.

The four men out of the five, for which we can find biographical records, are in many aspects exemplary of the modernising late Ottoman Empire and the Middle East: Coming from a plurality of religious and social backgrounds---Greek Orthodox, Catholic and Sunnī Muslim, priest and leading Salafi thinker of the second generation, part-time officials, of simple means and members of the old elites---they belonged to the same generation (born between the mid-1860s and mid-1870s) and worked as journalists, teachers, and occasionally politicians. All of them were highly mobile and well-travelled and had good command of local as well as foreign languages---to the extent that some of them published translations. The fifth man is not less exemplary, even though his story seems to be rather uncommon among journalists: Yūsuf Jirjis Zakham was one of the many emigrants from Greater Syria to America. He arrived in the USA in 1902 and was naturalised in 1904, settled in Lincoln, Nebraska, where he married Myra from Iowa and had at least five children. Both spouses were literate and Joseph George Zakem provided his profession as newspaper correspondent in the 1910 US Federal Census.[^43]

[^43]: {UnitedStatesCensus 1910}{UnitedStatesCensus 1920;UnitedStatesCensus 1930;UnitedStatesCensus 1940}

<!-- ![Figure: Word cloud of authors published in *al-Muqtabas*; by number of articles](assets/plots/word-cloud_muqtabas-authors-bylines.png) -->

The map of relative frequencies of locations mentioned in bylines conveys the same image as the network of referenced periodicals and the brief comments on the most prolific authors' biographies: *al-Muqtabas* was a publication of at least regional importance. It reached well beyond Greater Syria to Egypt, Iraq and even America, turning the famous proverb "Cairo writes, Beirut publishes and Baghdad reads" upside down with Baghdad well ahead of even Damascus.

![Figure: Locations in bylines in *al-Muqtabas* (Cairo and Damascus)](assets/plots/map-oclc_4770057679-bylines-middle-east.png)

#### *al-Ḥaqāʾiq*

The picture is different for *al-Ḥaqāʾiq*, which was repeatedly in conflict with *al-Muqtabas* over the latter's supposed moral laxity. Its most prolific contributors were Damascene Sunni religious scholars from notable families, many of whom were at least one generation older than its opponents (the average year of birth for *al-Ḥaqāʾiq* is 1837 and 1869 for *al-Muqtabas*). Among them are Ibrāhīm Mardam Bek, Muḥammad ʿĀrif al-Munīr al-Ḥusaynī (b.1847/48), Mukhtār al-Muʾayyad (b.1822) and Muḥammad al-Qāsimī (b.1843), whose son Jamāl al-Dīn al-Qāsimī was among *al-Muqtabas*' contributors. The initially surprising finding of very limited overlap between the two networks of authors published in journals from the same city, becomes less so against this backdrop. Looking at the top 14 contributors to both journals, we can also note that whereas only two authors from *al-Muqtabas* are missing from VIAF and thus international library catalogues, the same is true for eight of *al-Ḥaqāʾiq*'s most frequent authors.{>>This further affirms the difference between a journal with transregional impact and a more parochial periodical<<}

| rank |                author.id.viaf                |     author.name      | author.birth | author.death | article.count |
|------|----------------------------------------------|----------------------|--------------|--------------|---------------|
|    1 | NA                                           | NA                   | NA           | NA           |           286 |
|    2 | NA                                           | عبد الرحمن القصار    | 1863         | c.1931       |             8 |
|    3 | NA                                           | إبراهيم خليل مردم بك | NA           | NA           |             7 |
|    4 | [299025643](https://viaf.org/viaf/299025643) | محمد عارف المنير     | 1847/48      | 1923/24      |             5 |
|    5 | [53094077](https://viaf.org/viaf/53094077)   | محمد فريد وجدي       | 1875         | 1954         |             5 |
|    6 | [58892856](https://viaf.org/viaf/58892856)   | صالح الشريف          | 1869         | 1920         |             4 |
|    7 | NA                                           | ع                    | NA           | NA           |             4 |
|    8 | [51567828](https://viaf.org/viaf/51567828)   | محمد  القاسمي الحلاق | 1843         | 1900         |             4 |
|    9 | NA                                           | محمد سليم الحنفي     | NA           | NA           |             4 |
|   10 | [267054449](https://viaf.org/viaf/267054449) | مختار المؤيد         | 1822         | 1921         |             4 |
|   11 | NA                                           | أبو الضيا            | NA           | NA           |             3 |
|   12 | NA                                           | أحمد الجوبري         | NA           | NA           |             3 |
|   13 | NA                                           | احمد الباشا          | NA           | NA           |             3 |
|   14 | NA                                           | صلاح الدين الزعيم    | NA           | NA           |             3 |
|   15 | [60500457](https://viaf.org/viaf/60500457)   | أحمد محرم            | 1877         | 1945         |             2 |

Table: The fifteen most prolific authors in *al-Ḥaqāʾiq* by number of bylines

A map of the relative frequency of locations mentioned in bylines confirms the brief overview of the authors' biographies---*al-Ḥasnāʾ* was a parochial paper with a focus on local issues. Its geographic network was mainly restricted to Damascus itself and the cities of the Syrian hinterland.

![Figure: Locations in bylines in *al-Ḥaqāʾiq* (Damascus)](assets/plots/map-oclc_644997575-bylines-middle-east.png)

#### *Lughat al-ʿArab*

{==missing paragraph==}{>>comment on the most prolific authors in *Lughat al-ʿArab*<<}

| rank |                           author.id.viaf                           |        author.name         | author.name.transliterated | author.birth | author.death | word.count | article.count |
|------|--------------------------------------------------------------------|----------------------------|----------------------------|--------------|--------------|------------|---------------|
|    1 | NA                                                                 | NA                         | NA                         | NA           | NA           |     205355 |           787 |
|    2 | NA                                                                 | كاظم   الدجيلي             | kaZm   aldjyly             | 1884         | 1970         |      37233 |            27 |
|    3 | [97152636060620050511](https://viaf.org/viaf/97152636060620050511) | رزوق  عيسى                 | rzwQ  3ysA                 | 1885         | 1940         |      17303 |            16 |
|    4 | [21058435](https://viaf.org/viaf/21058435)                         | سليمان  الدخيل             | slyman  aldKyl             | 1877         | 1945   |      20005 |            15 |
|    5 | NA                                                                 | إبراهيم  حلمي  العمر       | abrahym  7lmy  al3mr       | 1890         | 1942         |      20550 |            13 |
|    6 | NA                                                                 | إبراهيم  منيب  الباججي     | abrahym  mnyb  albajjy     | NA           | NA           |       1733 |            13 |
|    7 | NA                                                                 | محمد  الهاشمي              | m7md  alhaWmy              | NA           | NA           |       1883 |             5 |
|    8 | NA                                                                 | محمد  باقر  الشبيبي        | m7md  baQr  alWbyby        | 1889         | 1960         |       3108 |             4 |
|    9 | [22006374](https://viaf.org/viaf/22006374)                         | محمد  رضا  الشبيبي         | m7md  rDa  alWbyby         | 1889   | 1965   |       4192 |             4 |
|   10 | [76496271](https://viaf.org/viaf/76496271)                         | جرجي  زيدان                | jrjy  zydan                | 1861   | 1914   |       6863 |             3 |
|   11 | NA                                                                 | عراقي                      | 3raQy                      | NA           | NA           |       3245 |             3 |
|   12 | NA                                                                 | عمانوئيل فتح الله عمانوئيل | 3manw5yl ft7 allh 3manw5yl | NA           | NA           |       2916 |             3 |
|   13 | NA                                                                 | البر كسبرخان               | albr ksbrKan               | NA           | NA           |       1703 |             2 |
|   14 | NA                                                                 | شكري الفضلي                | Wkry alfDly                | NA           | NA           |       3940 |             2 |

Table: The fifteen most prolific authors in *Lughat al-ʿArab* by number of bylines

There is only limited significance in a map of relative frequency of locations mentioned in bylines for *Lughat al-ʿArab*. Only 26 of 939 articles in our corpus provided a location.

{==![Figure: Locations in bylines in *Lughat al-ʿArab* (Baghdad)](assets/plots/map-oclc_472450345-bylines-middle-east.png)==}{>>remove this map<<}

<!-- ### *al-Ḥasnāʾ*? -->

<!-- ![Figure: Locations in bylines in *al-Ḥasnāʾ* (Beirut)](assets/plots/map-oclc_792756327-bylines-middle-east.png) -->

# Authorship attribution

The final part of this paper is dedicated to the gap in authorship attribution. Surprisingly the question of authorship has not received much attention.[^61] The, often implicit and accepted, hypothesis is that a periodical's editors authored all articles for which they did not provide a meaningful byline.[^62] 

This hypothesis raises a number of problems and considerations. First and foremost it remains untested. 
Second, we simply do not know enough about any given periodical to even name all the {~~formal collaborators~>editors~~}. Cover pages of journals and mastheads of newspapers had a limited vocabulary to state responsibilities for an issue, not all of which were always provided: *owner* or *concessionary* (*ṣāḥib*, *ṣāḥib al-imtiyāz*), *responsible director* (*al-mudīr al-masʾūl*) and *editor-in-chief* (*raʾis al-taḥrīr*).[^68] Commonly these functions converged and periodicals provided only a single name. 
Third, is highly unlikely that a single person authored and edited almost the complete content of a periodical in addition to operating the whole business of {~~printing, distribution, acquisitions of adverts~>publishing~~}. Some owners-cum-editors ran more than one periodical. Muḥammad Kurd ʿAlī, for instance, published a daily of four pages in addition to his monthly journal. We must therefore conceptualise potential authorship by editors as a collaborative {>>or communal<<} endeavour. 
Fourth, owner-cum-editors were repeatedly absent from the place of publication and printing and it is hard to believe they would have run their periodicals via the telegraph. Either a periodical suspended publication during their absence or it must have been produced by someone else in their stead.[^65] In the case of *al-Muqtabas*, we know that Muḥammad Kurd ʿAlī fled Damascus and the Ottoman Empire twice for extended periods of time due to conflicts of his newspaper {>>*al-Muqtabas*<<} with the {==censors==}{>>authorities<<}. While the newspaper was suspended between September 1909 and March 1910 as well as between April and August 1912, Kurd ʿAlī fled to Egypt and travelled through Europe. He wrote letters about his observations which were serialised in his periodicals as *gharāʾib al-gharb* (Oddities of the West) and *fī diyār al-gharb* (Countries of the West) and later published in book form. The consequence of his absences on his potential authorship for articles in *al-Muqtabas* is not entirely clear. This is partially due to the difficulty of establishing actual publication dates as alluded to above.  In 1909/10 the publication of *al-Muqtabas* corresponded with Kurd ʿAlī's absence from Damascus[^63], while during the latter period the publication {--of the final seven issues of volume seven of--} {==*al-Muqtabas* moved to Cairo==}{>>how did they do that?<<}---yet, Kurd ʿAlī was travelling through Europe and can therefore not be assumed as the main editor.[^64]
On a more empirical level, we can find repeated calls from multiple periodicals on authors of anonymously submitted contributions to come forward and provide their identities to the publishers.[^66] In a similar vein, the newspaper *al-Muqtabas* rejected allegations that articles published by pseudonymous authors were indeed authored by the editors.[^67]

<!-- + the *mudīr al-masʾūl* was personally liable for any article published in his periodical. Not being able to produce the author of a text would mean being prosecuted alone. However, since he was treated like the author by law, this could have been a strategy to not give up names. -->

[^61]: The problem is not even mentioned in {Ayalon 1995}.

[^62]: For examples of this implicit hypothesis see {Seikaly 1981@130, 131}, where he assigns a number of anonymous articles in *al-Muqtabas* to Muḥammad Kurd ʿAlī without even discussing his assumption. {Czygan 2012@120} makes the same assumption by stating that it wasn't entirely clear if Ḍiyā Bey authored the final 36 issues of the journal *Ḥürriyet* all by himself.

[^63]: {al-quds-1-60@4} paraphrased an [article in *al-Muqtabas* 4(2)](https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_38.TEIP5.xml#div_25.d1e4565), which was slated for February/March 1909 according to its masthead. The back cover of *al-Muqtabas* 4(4) articulates the hope that no. 4(5) and 4(6) would be published as a double issue in mid-August 1909 (mid-Shaʿbān 1327 aH). Yet, no. 4(7) was published only in the first week of April 1910; {muqtabas 76-eap@3}.

[^64]: [*al-Muqtabas* 7(6):496](https://tillgrallert.github.io/digital-muqtabas/xml/oclc_4770057679-i_77.TEIP5.xml#div_14.d1e4462).

[^65]: {Ayalon 1995@224} provides examples of two journals informing their readers that they will have to publish double issues due to absences of their publishers. [*al-Zuhūr* 1(8):368](https://openarabicpe.github.io/journal_al-zuhur/tei/oclc_1034545644-i_7.TEIP5.xml#div_1.d2e2020) apologises to its readers for the delay in publishing this issue because the editor was travelling outside Egypt/Cairo {>>to Beirut<<}.

[^66]: E.g. {thamarat 181; lisan 442; lisan 1301; thamarat 573; thamarat 729}.

[^67]: Instead, they claimed, not all *ʿulamāʾ* and *udabāʾ* in support of progress can speak out; {jarmuq 51@3}.

[^68]: The earliest Ottoman press codes mandated identifiable information on a periodical's publisher as well as the legal responsibility of the person signing off on the bottom of the (last) page for any paper's content as if he was the author; {DüsturKavaninVeNizamat 1872j}. The function and responsibilities of the *mudīr masʾūl* were stipulated by {DüsturKavaninVeNizamat 1909}.


## Stylometry

What are the computational means for casting some light on the more than four fifths of articles without authorship information and to test the hypothesis that editors were indeed the authors of unattributed texts? 

A common approach in linguistics and literary studies is the analysis of "style" based on the observation "that authors tend to write in relatively consistent, recognizable and unique ways", which is particularly true for an author's vocabulary.[^14] Computational stylistics or stylometry is one of the methods frequently referred to as *distant reading*[^13] and can be summarised as the statistical analysis of literary style for the purpose of authorship attribution and genre detection, whereby "style" commonly means a frequency count of vocabulary used in a given text.[^11] Stylometry then computes degrees of similarity between texts, called distance measure, through comparing multivariant frequency lists of textual features. The important catch is that in order to establish similarities one has to have access to a significant corpus of digital texts by authors likely to be found among the unattributed texts. If we only compare every article in our periodical corpus to every other article in the same corpus, we cannot possibly identify any author not yet named in a byline. Instead, the best we could hope for would be to establish groups of texts that have a certain likelihood of having been authored by the same person.

[^14]: {Laramée 2018}

[^13]: For a good summary of genealogy of large-scale literary history under the label "distant reading" see {Underwood 2017}. The most often referenced founding works are {Moretti 2013} (collection of reprinted essays), {Jockers 2013}.

[^11]: For an introduction to stylometry see {>>add references<<}

As far as I know there has only been one attempt at stylometric authorship attribution for Ottoman periodicals but, after developing a set of style markers for individual editors-cum-authors, the author did not apply them for actual authorship attribution.[^5] The present paper is the first foray into stylometric authorship attribution for Arabic periodicals.

[^5]: {Czygan 2012}. This work falls short on many counts beyond introducing a promising approach. Basic statistic measures about her corpus and computational approaches remain unknown and most importantly, she tested only one (sic!) anonymous article with a set of parameters she took 80 pages to develop.

There is some debate as to which style-markers and distance measure should be considered for authorship attribution, but <!-- throughout the following sections of this paper --> I settled on lists of Most Frequent Words (MFWs) and Burrow's Delta{--, which can be visualised as dendrograms--}.[^38] Unlike other forms of computational linguistics, texts should not be pre-processed by, for instance, morphologising or lemmatizing. All stylometric analysis  was done using the "stylo" package for R[^15] on plain-text exports from the TEI files.[^41] Results were then visualised using [Gephi](https://gephi.org).[^42]

Maciej Eder{--, inspired by phylogenetics,--} suggested to use *bootstrap consensus trees* and *consensus networks* in order to separate signal and noise and in order to overcome selection bias when picking from a range of dendrograms. In the latter method, one computes the nearest neighbour as well as the first two runners-up for a sequence of MFWs, let's say from 100 to 1000 MFWs in increments of 100, and then combine the results in a single output, which serves as a form of self-validation for the more robust signals. The results can then be visualised using network analysis.[^39] 
<!-- minimum length of texts -->
There has been some debate about the minimal required length for attribution. Eder ran a series of stylometric analyses on medium-sized corpora of prose texts in English, Polish, German, Hungarian, Latin and Greek using Burrow's Delta on 200 MFWs in order to experimentally establish a threshold length. He found that 5000 words is the minimal length for meaningful attribution below which the signal is "immensely affected by random noise".[^40] {--Yet, contrary to common assumptions that longer text will lead to ever improving attribution results, Eder also established that beyond a length of 15000 words accuracy of authorship attribution does not improve any further.--} 
These findings have severe implications for the application of stylometry to periodicals---most texts are much shorter than 5000 words and even the longer ones are too short for random sampling. Nevertheless, our first experiments with stylometric analysis yielded promising results and show at least three distinct signals: genre, author and translator/editor.

| article length | number of articles |
|----------------|--------------------|
| > 5000         |                 50 |
| 2001--5000     |                297 |
| 1000--2000     |                449 |

Table: Length of articles in our corpus

[^15]: {Eder 2016b}
[^38]: {==missing footnote==}{>>footnote on Burrow's Delta<<}
[^39]: {Eder 2017}
[^40]: {Eder 2015@170}
[^41]: {==missing footnote==}{>>footnote on my pre-processing pipeline<<}
[^42]: {Bastian 2009}

## Results
<!-- ### stylometry confirms what we already know  -->

An initial analysis of all articles of 5000 words and more using bootstrap consensus trees for 100--1000 MFWs confirms the general applicability of stylometry to our corpus. Articles form clusters based on edge weight and modularity {>>number of edges among members higher than to other clusters<<} around authors, editors and translators. Thus, we find clusters of articles authored by Jamāl al-Dīn al-Qāsimī, Aḥmad Zakī, Charles Seignobos and Muḥammad Kurd ʿAlī. The latter was the translator of Seignobos works from French, which is clearly visible in the clustering of works by both authors on the right of the plot. A similar clustering appears on the left of the plot where one can observe a proximity between works authored by Jamāl al-Dīn al-Qāsimī ({==dark green==}) and classic texts he discovered and edited ({==pink==}). The plot shows only limited {==stylistic overlap==}{>>in terms of modularity and edge weights<<} between authors and we can assume with a high degree of confidence that the cluster of anonymous articles in {==light green==} on the bottom right was authored by Kurd ʿAlī. Since the sample contains almost exclusively articles from *al-Muqtabas*, this would tentatively confirm the authorship hypothesis of editors. However, this plot also shows a {==red==} cluster of non-attributed articles in the centre that are stylistically distinct from Kurd ʿAlī's texts. This contradicts the hypothesis and points to another, unknown author. 

Furthermore, the plot also shows a strong signal of genre: the {==light green==} cluster of texts most likely written by Kurd ʿAlī are all geographic works.

![Figure: bootstrap consensus network, colours by modularity group](assets/plots/stylo_articles-w_5000-modularity_1-label_authors-ar.png)

{--Our initial submission of a corpus of all articles longer than 3000 words to stylometric analysis using bootstrap consensus trees for 100--1000 MFWs confirmed the methods' usefulness by establishing clusters of: a) texts from the same authors or translators; b) serialised texts with or without explicit authorship information; c) texts within the same genre, such as travelogues or *qaṣāʾid*; d) manuscripts by different authors but with the same editor.--}

{--![Figure: bootstrap consensus network, colours by modularity group](assets/plots/stylo_oape-commented_2019-10-04_modularity.png)--}

<!-- attempts to overcome the 5000 word limit -->

Stylometric analysis of individual articles is severely limited by the minimum length for reliable authorship attribution because the vast majority of articles in our corpus fall below the threshold of 5000 words. However, most journals published shorter articles {==based on other publications, announcing publications etc.==}{>>change or cut<<} in sections. One can analyse these articles as originally aggregated in sections to test the hypothesis that they were all authored by the journals' editors. To do so, I aggregated all articles in sections on the issue level, submitted them to stylometric analysis and looked for clustering by periodical. {--This workaround is necessary since we neither know all actual editors working at a journal, nor do we have corpora of digital texts for all known editors. Otherwise these could be directly compared to the sections.--}

<!-- ![Figure: bootstrap consensus network of sections of articles in 123 periodical issues based on consensus of 100–1000 MWFs, coloured by periodical title](/BachUni/BachBibliothek/GitHub/OpenArabicPE/OpenArabicPE_analysis/stylometry/OpenArabicPE/visualisations/consensus-tree/sections/sections_Consensus_100-1000_MFWs_Culled_0__wurzburg_C_0.5_journals.png) -->

![Figure: bootstrap consensus network of sections of articles in 123 periodical issues based on consensus of 100–1000 MWFs, coloured by modularity](assets/plots/stylo_sections_Consensus_100-1000_MFWs_Culled_0__wurzburg_C_0.5_modularity.png)

The bootstrap consensus network of sections (100-1000 MWFs) clearly shows clustering along periodicals based on edge weight{-- (i.e. similarity) connecting sections--}. In the plot below *al-Muqtabas* is on the left, *al-Ḥaqāʾiq* in the centre and *Lughat al-ʿArab* to the right. The plot shows that, as far as articles in sections were concerned, each periodical is stylistically distinguishable from the others. The plot also shows clusters of sections inside *al-Muqtabas*. Nodes inside these clusters are {==stylistically closer==}{>>more connections between themselves than to the outside<<} to each other than to other clusters (modularity). 

<!-- final analysis: compare sections in al-Muqtabas to articles (w_5000) by Muḥammad Kurd ʿAlī -->

{>>modularity<<} 

# Conclusion
<!-- ## Summary -->

In this paper, I questioned hyperbolic promises of ubiquitous digitised knowledge from the marginal position of Middle Eastern intellectual history and by outlining the techno-infrastructural challenges faced by a {=="digital history"==}{>> or computational approaches to the material artefacts<<} of societies outside the Global North. I showed, how a digital episteme deeply rooted in 20th-century, english-speaking, American neoliberal capitalism requires mitigation strategies on every level of the digital workflow. These are placed on the individual scholar and involve significant investments in the making of corpora, resources and tools if we want to reap the promised fruits of the digital humanities. I also posed that one of the consequences of this episteme is a neo-orientalist silencing of the material heritage of the societies in the Eastern Mediterranean.

Nevertheless, digital corpora and computational approaches are indispensable for scrutinising the periodical press as an ideosphere. I argued that one has to transcend the individual periodical and engage in a systematic study of the periodical press at scale in order to better understand both the intellectual history of the Eastern Mediterranean and periodical production itself. The case study of a corpus of four late Ottoman Arabic-speaking periodicals from the Eastern Mediterranean and comprising *al-Muqtabas*, *al-Ḥaqaʾiq*, *Lughat al-ʿArab* and *al-Ḥasnāʾ* introduced and evaluated some of the mitigation strategies.  After introducing my own efforts of building an open and scholarly digital corpus, I engaged in computational exploration through network analysis, mapping, and stylometry along the guiding question of what were the core nodes (authors and periodicals) in the ideoscape of the late Ottoman Eastern Mediterranean?


{>>The paper also presents the first application of methods of *distant reading* to the study of late Ottoman Arabic periodicals.<<}

<!-- ## Results -->

Modelling the network of references to periodical titles, I could confirm established knowledge about the importance of certain journals over others. The Cairene journals of *al-Manār*, *al-Muqtaṭaf* and *al-Hilāl* are central to the late Ottoman Arabic ideosphere, even though they were published outside the Ottoman Empire {>>Egypt is de facto independent of the Ottoman Empire<<}. A future systematic exploration of periodicals will have to digitise these and compare them to *al-Muqtabas*, which shows many traits of a periodical of transregional importance very different from the other journals in our corpus. 

The exploration of the network of article authors{-- published in our corpus--}, on the other hand, provided a number of surprising results that will need to be addressed in future scholarship: The noted importance of Iraqi writers over Syrians among the core nodes of the network contradicts the common narrative about the Arabic renaissance (*nahḍa*). A similar importance of Baghdad over the more commonly assumed centres of Arab intellectual production is found in the geographic distribution of toponyms in bylines for *al-Muqtabas*. One would, again, need to test other transregional periodicals to see whether they provide a similar Iraqi connection or if *al-Muqtabas* is an outlier in this regard. The network analysis of authors also demonstrated lacunae in the historiography of the Arabic press and the intellectual history of the late Ottoman Arab ideosphere, namely the absence of the core nodes in our network from major works of scholarship.

Noting that any analysis of authorship and socio-intellectual networks is limited by the fact that less than one fifths of all articles carry identifiable authorship information, I finally submitted our corpus to stylometric analysis. This provided  significant hints towards authors of the small number of anonymous articles longer than 5000 words. Testing the hypothesis that a journal's editors were the actual authors of anonymous texts, the results are inconclusive. We found one cluster of texts by an anonymous author very different from those that can indeed by attributed to the editor by looking at the articles of more than 5000 words in *al-Muqtabas*.


{--- limited overlap between journals from the same city--}
{>>- impossibility of confirming editors as authors at this point
- This is the first application of stylometry to Arabic <<}


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
