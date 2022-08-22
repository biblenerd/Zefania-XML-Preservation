# Zefania XML Bible Markup Language Preservation

A repo to store data and information related to Zefania XML for preservation purposes.

**Zefania XML** is an XML-based markup language used for describing Bible texts. It enables applications that understand XML to read and process these texts. Zefania XML is available under the [GNU General Public License (GPL)](https://github.com/biblenerd/Zefania-XML-Preservation/blob/main/LICENSE). The format is designed to be simple for ease of sharing Bible texts. Zefania XML was originally created by the Theological Initiative Freiburg for the benefit of Bible software developers targeting German-speaking users.


## Contents

- [XML Structure](#xml-structure)
  - [Elements](#elements)
  - [Attributes](#attributes)
  - [Declaration](#declaration)
  - [Example excerpt](#example-excerpt)
- [Projects that use or support Zefania XML](#projects-that-use-or-support-zefania-xml)
- [Why this repo?](#why-this-repo)
  

## XML Structure

The domain associated with the XML schema documentation is no longer maintained, but the former content can be viewed via an [archived version](https://web.archive.org/web/20180730154206/http://bgfdb.de/zefaniaxml/bml/). I was able to find a copy of the XSD file at the [BibleWorkPlace Zefania XML 2014 repo](https://sourceforge.net/p/bibleworkplace/zef2014/ci/master/tree/), and have also backed the XSD file and ISO codes in this repo.

Below are some of the basics of this XML format but this is by no means comprehensive documentation.

### Elements

Zefania XML follows standard book, chapter, and verse logical divisions in Bible texts and describes them with the following nested elements:

- `<XMLBIBLE>` Marker for the entire Bible text document. `</XMLBIBLE>`
  - `<BIBLEBOOK>` Marker for the boundary of a Bible book. `</BIBLEBOOK>`
    - `<CHAPTER>`  Marker for chapter boundaries within a Bible book. `</CHAPTER>`
      - `<VERS>` Marker for verse boundaries within a Bible chapter. `</VERS>`

There is also an `<INFORMATION>` element containing a declaration about the Bible text, which is described in the [Declaration section](#declaration) below. 

### Attributes

These XML elements have attributes, the most common of which are illustrated within each of the above-listed corresponding elements as follows: 

**Associated Element**|**Attribute**|**Description**|**Example Value**
:-----:|:-----:|:-----:|:-----:
XMLBIBLE |biblename |Name of the Bible text |"King James Version"
BIBLEBOOK |bnumber |Bible book number |"1"
BIBLEBOOK |bname |Bible book name |"Genesis"
BIBLEBOOK |bsname |Bible book short name |"Gen"
CHAPTER |cnumber |Bible chapter number (relative to book) |"1"
VERS |vnumber |Bible verse number (relative to book and chapter) |"1"

There are also other available attributes for formatting, references to other Bible passages, translation and grammar notes, etc. 

### Declaration

As with any XML document, Zefania XML requires a declaration and namespace reference. There is also an `<INFORMATION>` element in which bibliographic data are stored following the [Dublin Core standard](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/). An example <INFORMATION> section for the King James Bible follows:

    <INFORMATION>
      <title>King James Version</title>
      <creator>Richard Bancroft (editor)</creator>
      <subject>The Holy Bible</subject>
      <description>This is an example description for the Wikipedia article on Zefania XML. This is the 1611 King James Version of the Bible, sometimes referred to as the Authorized Version.</description>
      <publisher>Wikipedia</publisher>
      <contributors>King James VI and I</contributors>
      <date>2022-08-17</date>
      <type>Bible</type>
      <format>Zefania XML Bible Markup Language</format>
      <identifier>KJV</identifier>
      <language>ENG</language>
      <rights>Public Domain</rights>
    </INFORMATION>

### Example excerpt

Below is an excerpted example representing the first two verses of the Gospel of John 1:1–2 in the King James Version Bible along with appropriate declaration and bibliographic data: 

    <?xml version="1.0" encoding="utf-8"?>
    <XMLBIBLE biblename="King James Version">
      <INFORMATION>
        <title>King James Version</title>
        <creator>Richard Bancroft (editor)</creator>
        <subject>The Holy Bible</subject>
        <description>This is an example description for the Wikipedia article on Zefania XML. This is the 1611 King James Version of the Bible, sometimes referred to as the Authorized Version. This excerpted Bible only contains the first two verses of the Gospel of John for illustrative purposes.</description>
        <publisher>Wikipedia</publisher>
        <contributors>King James VI and I</contributors>
        <date>2022-08-17</date>
        <type>Bible</type>
        <format>Zefania XML Bible Markup Language</format>
        <identifier>KJV</identifier>
        <language>ENG</language>
        <rights>Public Domain</rights>
      </INFORMATION>
      <BIBLEBOOK bnumber="43" bname="John" bsname="John">
        <CHAPTER cnumber="1">
        <VERS vnumber="1">In the beginning was the Word, and the Word was with God, and the Word was God.</VERS>
        <VERS vnumber="2">The same was in the beginning with God.</VERS>
        </CHAPTER>
      </BIBLEBOOK>
    </XMLBIBLE>


## Projects that use or support Zefania XML

- [Zefania XML bible modules](https://sourceforge.net/projects/zefania-sharp/) &mdash; SourceForge repository contains over 100 Bibles in Zefania XML format. These files are backed up in this repo as well.

- **ZefaniaBible.com** &mdash; The main website for reading Bibles stored in Zefania XML format no longer appears to be available, but code for the project is still available on GitHub:
  - [NothinRandom/Zefania-Bible](https://github.com/NothinRandom/Zefania-Bible) (last commit in 2013)
  - [apachesep/Zefania-Bible](https://github.com/apachesep/Zefania-Bible) (last commit in 2015 and appears to have more plugins)

- [Bible - Offline translations Android app](https://play.google.com/store/apps/details?id=sk.nosal.matej.bible)

- [Die Online Bibel website](http://dieonlinebibel.de/)

- [OpenAjax Bible Reader web app](https://www.mathertel.de/AJAXEngine/S03_AJAXControls/BiblePage.aspx#version=&book=&chapter=)

- [Simple Bible Reader](https://trumpet-call.org/simplebiblereader/)

- [The Word Bible Software](https://www.theword.net/index.php)

- Church projection software tools that support Zefania XML:
  - [Easyslides](https://www.easyslides.com/main/v5/bibles/)
  - [OpenSong](http://www.opensong.org/home/download#bibles)
  - [SongBeamer](https://www.songbeamer.com/software.htm)
  - [Quelea](https://quelea.org/)
  - [VerseVIEW](http://verseview.info/verseview/?p=951)

- There are also tools that can convert Zefania XML into other formats:
  - [schierlm/BibleMultiConverter](https://github.com/schierlm/BibleMultiConverter) (GitHub repo)
  - [Freely-Given.org Bible Drop Box](https://freely-given.org/Software/BibleDropBox/)


## Why this repo?

A lot of links associated with Zefania XML are now dead. I wrote a Wikipedia article about Zefania XML to preserve some basic information about it but the submission was declined due to the article not being supported by reliable sources. I figured it would be a shame for the information to perish, so preserved it here and decided to also back up and/or clone associated data that I identified as well in case the websites or repos currently hosting them become defunct (a little redundancy doesn't hurt).
