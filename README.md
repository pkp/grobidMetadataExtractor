# grobidMetadataExtractor

A plugin integrating Grobid for early automated metadata extraction from OJS submission files. It is compatible with OJS 3.6.

Known issues:
- When extracted author metadata does not meet the required minimum data for authors, the submitter is not guided clearly back to the author data for correction on the submission review page.

# Configuration additions

The `config.inc.php` configuration file should be configured with details for both Unoconv (or equivalent) and Grobid.

```
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
; Grobid Metadata Extractor ;
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

[grobidMetadataExtractor]

; Path to the Unoconv binary that can be used to convert documents to PDF for Grobid ingestion.
unoconv = /usr/bin/unoconv

; When set to On, submissions will be re-grobidded every time a submission file is edited.
; (Otherwise, they are stamped the first time a conversion is completed, and will not be touched subsequently.)
repeat = On

; URL to the Grobid web service.
grobid_api_url = "http://localhost:8070/api/processHeaderDocument"
```
