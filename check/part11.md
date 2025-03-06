---
abstract: [21 CFR Part 11](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/part-11-electronic-records-electronic-signatures-scope-and-application) is required of some OU REDCap projects, notably the projects containing data from clinical trials.  This chapter describes the elements that a research team (_i.e._, not Vanderbilt or OU's OCRI) is responsible for.

author:
  - name: Thomas Wilson
    affiliation: University of Oklahoma Health Sciences
    affiliation-url: https://ouhsc.edu/bbmc/
    email: thomas-wilson@ouhsc.edu
    orcid: 0009-0009-1239-1348
  - name: William H Beasley
    affiliation: University of Oklahoma Health Sciences
    affiliation-url: https://research.ouhsc.edu/ocri
    email: wibeasley@hotmail.com
    orcid: 0000-0002-5613-5006

csl: ../assets/csl/apa-7e.csl
---

# 21 CFR Part 11 Requirements of the Researcher {#sec-check-part11}

**Chapter Leads**: Thomas Wilson

## G. RECORD RETENTION

### 2. LONG-TERM ACCESSIBILITY

#### c. Are file formats chosen to ensure long-term readability (e.g., PDF, CSV)?

REDCap provides at least 10 different export formats,
ranging from the highly-portable (_e.g._, *.csv: comma separate value)
to specialized and proprietary (_e.g._, *.sas7bdat: SAS files).

To promote portability and long-term usefulness,
we recommend exporting data as a csv.
Even if you want something specialized in the short-term (_e.g._, an SPSS file),
we recommend exporting and storing second copy (as a csv) to improve the options available
to others in the future.
