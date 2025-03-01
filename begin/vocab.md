---
abstract: Vocabulary that will help beginning users.

author:
  - name: Thomas Wilson
    affiliation: University of Oklahoma Health Sciences
    affiliation-url: https://ouhsc.edu/bbmc/
    email: thomas-wilson@ouhsc.edu
    orcid: 0009-0009-1239-1348
    attributes:
      corresponding: true

csl: ../assets/csl/apa-7e.csl
---

# Vocabulary {#sec-begin-vocab}

**Chapter Leads**: Thomas Wilson

## General {#sec-begin-vocab-general}

These general terms for beginners reading Chapters [-@sec-begin-support] through [-@sec-begin-security].

### Username {#sec-begin-vocab-general-username}

The credential required to login to REDCap.  This username will be one of three things: OUHSC username, OU username, or a table-based username for non-OUHSC collaborators.  Tabled-based accounts are created and maintained by OUHSC REDCap admins.

### Project {#sec-begin-vocab-general-project}

A REDCap project is a self-contained entity used for collecting and managing data.  Many people use the term, database, interchangeably.  REDCap users may have access to or may have created multiple REDCap projects.

### Server {#sec-begin-vocab-general-server}

A REDCap _server_ hosts a collection of [project](vocab.md#sec-begin-vocab-general-project)s.
Identifying the correct server is the first step to navigating
to your desired project.

At OU, the two production servers are
<https://bbmc.ouhsc.edu> and
<https://redcap.ouhsc.edu>.

The first is the newer and larger instance,
while the second one
(sometimes called the "CoPH server")
is being phased out and no longer accepting new projects.

Beginning users will rarely encounter OU's "development" server, which is <https://redcap-dev-2.ouhsc.edu>.

### Record {#sec-begin-vocab-general-record}

... distinguish w/ [event](vocab.md#sec-begin-vocab-general-event) and [participant](vocab.md#sec-begin-vocab-general-participant) ...

### Participant {#sec-begin-vocab-general-participant}

A _participant_ is sometimes synonymous with [record](vocab.md#sec-begin-vocab-general-record),
but not always...

### Data Collection Instrument (DCI or Instrument) {#sec-begin-vocab-general-instrument}

An electronic form used to collect data.  An instrument can have one of two configurations: an data collection form or a survey.

### Data Collection Form {#sec-begin-vocab-general-form}

Instrument used to collect data from behind the REDCap login.  To enter data using a data collection form, individuals must login to REDCap using their username and password.

### Survey {#sec-begin-vocab-general-survey}

Instrument used to collect data without a REDCap login.  Surveys are most often used to collect data from research participants and/or patients.  Surveys can have a unique link for each participant or a generic public survey link.

### Event {#sec-begin-vocab-general-event}

A REDCap _event_ is a nested inside a [record](vocab.md#sec-begin-vocab-general-record),
typically to facilitate longitudinal data collection within the same [participant](vocab.md#sec-begin-vocab-general-participant).

### User {#sec-begin-vocab-general-user}

Many types of REDCap *user*s can be interact with a single [project](vocab.md#sec-begin-vocab-general-project).
See @sec-adminpr-user-role-research for a list of common roles, ranging from a participant responding to a public survey to a project administrator.

::: {.callout-note appearance="simple"}

## Additional Chapter Details

This chapter was started in October 2024.
If you have suggested modifications or additions, please see [How to Contribute](../index.qmd#sec-welcome-contribute) on the book's welcome page.
:::
