SOU corpus
----------
This repository contains cleaned and further processed versions of Swedish Government Official Reports - Statens offentliga utredningar (SOU).
The documents are based on html versions from [Riksdagens öppna data](http://data.riksdagen.se) and cover the years 1994 to 2020.


## html/
In contrast to the original html versions, the extracted files distinguish section headers and titles from text body.
Tables, lists and diagrams as well as non-Swedish text were removed whenever they could be identified as such. The documents were split into summaries and full report. The filenames consist of a code for the type of text and the document id. The text codes are:

* **ft**: for full text
* **s**: for standard Swedish summary
* **SEs**: for simple Swedish summary
* **ENs**: for English summary

The original html can be found at `https://data.riksdagen.se/dokument/` + `document id`.
So for the file `ft_H4B319.html` the corresponding original file at Riksdagen is [`https://data.riksdagen.se/dokument/H4B319.html`](https://data.riksdagen.se/dokument/H4B319.html).

## tagged/
This directory contains sentence-segmented and dependency-parsed versions of the SOU-text bodies. These are saved as csv, with the second field containing a processed sentence at a time and the first field containing the corresponding raw section header or title.
For sentence segmentation and parsing, the [Swedish spaCy model](https://github.com/Kungbib/swedish-spacy) was used.
The sentence segmentation was complemented with some rules for

* abbreviations like 'm.m.', 'osv.' and 'etc.' that can to occur at the end of a sentence
* the use of a colon with acronyms to express possessive or plural (e.g. 'EU:s huvudmål ...', 'SOU:er', etc.)
