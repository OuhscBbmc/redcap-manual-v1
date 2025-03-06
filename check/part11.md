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

## System Validation And Change Control (Sec A) {#sec-check-part11-system}

RTs are not responsible for content in this section.

## Access Control And Security (Sec B) {#sec-check-part11-access}

### User Authentication (Subsec B1) {#sec-check-part11-access-authentication}

RTs are not responsible for content in this section.

### Role-Based Permissions (Subsec B2) {#sec-check-part11-access-role}

#### Are roles and permissions in REDCap configured to ensure that users only have the minimum necessary access to perform their job functions? {#sec-check-part11-access-role-minimum}

REDCap allows fine-grained permissions to users and groups within each project.

It is the RT's responsibility to assign other study team members the appropriate permissions,
while following the principles of [least privilege](https://en.wikipedia.org/wiki/Principle_of_least_privilege).

#### Are permission sets periodically reviewed to confirm they still align with user job functions? {#sec-check-part11-access-role-periodically}

Yes, the REDCap dashboard to allow someone to quickly review the study's users, groups, and permissions.
It is the RT's responsibility to periodically review this dashboard.

#### Do you enforce the principle of least privilege (admins vs. data entry vs. monitors)? {#sec-check-part11-access-role-least}

The RT works with their team members and should be aware of their roles approved by the IRB.

It is the RT's responsibility to assign the appropriate levels of privileges.

## Record Retention (Sec G) {#sec-check-part11-retention}

### Long-Term Accessibility (Subsec G2) {#sec-check-part11-retention-accessibility}

#### Are file formats chosen to ensure long-term readability (e.g., PDF, CSV)?{#sec-check-part11-retention-accessibility-longterm}

REDCap provides the export formats shown in @fig-check-part11-200-export-formats,
ranging from the highly-portable (_e.g._, .csv: comma separate value)
to the specialized and proprietary (_e.g._, .sas7bdat: SAS files).

To promote portability and long-term usefulness,
we recommend exporting data as a csv.
Even if you want something specialized in the short-term (_e.g._, an SPSS file),
we recommend exporting and storing second copy (as a csv) to improve the options available
to others in the future.

![Data Export Formats.](images/part11/fig-check-part11-200-export-formats.png){#fig-check-part11-200-export-formats width=50% fig-alt="Data Export Formats"}
