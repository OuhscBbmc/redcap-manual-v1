---
abstract: >
  [21 CFR Part 11](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/part-11-electronic-records-electronic-signatures-scope-and-application) is required of some OU REDCap projects, notably the projects containing data from clinical trials.  This chapter describes the elements that a research team  (RT; _i.e._, not Vanderbilt or OU's OCRI) is responsible for.

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

Glossary:

* _RA_: REDCap Administrators.
  OU employees that are responsible for the overall instance on campus.
  This includes some [OCRI](https://research.ouhsc.edu/ocri) employees (like Thomas Wilson)
  train users and manage the back-end servers.
  It also includes OU IT employees who are experts in virtual servers and Linux.

* _RD_: REDCap Developer. Vandy {Come back to this.}

* _RT_: Research Team.
  These are the people managing the research project.
  Their typical duties include designing the study, collecting data, analyzing the results, and publishing the findings.

  These are the individuals who are responsible for the daily operations of the study,
  and how a study is reflected in a REDCap project.

  The RT is different from the people who design the REDCap software (at Vanderbilt University) and
  from the people who administer the local REDCap instance (in OCRI and OU IT).

## A. SYSTEM VALIDATION AND CHANGE CONTROL

RTs are not responsible for content in this section.

## B. ACCESS CONTROL AND SECURITY

### 1. USER AUTHENTICATION

RTs are not responsible for content in this section.

### 2. ROLE-BASED PERMISSIONS

#### a. Are roles and permissions in REDCap configured to ensure that users only have the minimum necessary access to perform their job functions?

REDCap allows fine-grained permissions to users and groups within each project.

It is the RT's responsibility to assign other study team members the appropriate permissions,
while following the principles of [least privilege](https://en.wikipedia.org/wiki/Principle_of_least_privilege).

#### b. Are permission sets periodically reviewed to confirm they still align with user job functions?

Yes, the REDCap dashboard to allow someone to quickly review the study's users, groups, and permissions.
It is the RT's responsibility to periodically review this dashboard.

#### c. Do you enforce the principle of least privilege (admins vs. data entry vs. monitors)?

The RT works with their team members and should be aware of their roles approved by the IRB.

It is the RT's responsibility to assign the appropriate levels of privileges.

## G. RECORD RETENTION

### 2. LONG-TERM ACCESSIBILITY

#### c. Are file formats chosen to ensure long-term readability (e.g., PDF, CSV)?

REDCap provides at least 10 different export formats,
ranging from the highly-portable (_e.g._, .csv: comma separate value)
to specialized and proprietary (_e.g._, .sas7bdat: SAS files).

To promote portability and long-term usefulness,
we recommend exporting data as a csv.
Even if you want something specialized in the short-term (_e.g._, an SPSS file),
we recommend exporting and storing second copy (as a csv) to improve the options available
to others in the future.
