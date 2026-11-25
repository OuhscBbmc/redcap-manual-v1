---
abstract: Help avoiding problems to production data

author:
  - name: Will Beasley
    affiliation: University of Oklahoma Health Campus
    affiliation-url: https://ouhsc.edu/bbmc/
    email: wibeasley@hotmail.com
    orcid: 0000-0002-5613-5006

  - name: Thomas Wilson
    affiliation: University of Oklahoma Health Campus
    affiliation-url: https://ouhsc.edu/bbmc/
    email: thomas-wilson@ou.edu.
    orcid: 0009-0009-1239-1348
    attributes:
      corresponding: true

csl: ../assets/csl/apa-7e.csl
---

# Proposed Changes to a Project in Production {#sec-trouble-productionchanges}

**Chapter Leads**: Will Beasley

## Introduction {#sec-trouble-productionchanges-introduction}

When a REDCap project is in production,
the software provides several features to protect a project admin
from accidentally corrupting or destroying valuable data
that might be impossible to recollect.
If you are unfamiliar with the process of moving a project to production,
please first read @sec-check-testing-production.

When changes are desired to a production project:

1. a project admin initially places the project design in _Draft Mode_. Next,
1. the project is altered (eg, adding a new variable, rewording a multiple-choice option). Then,
1. the proposed changes from the _project admin_ are submitted to the _server admin_. And finally,
1. the server admin reviews the proposals before deciding to accept or reject all the changes at once.
   There is not a mechanism that allows acceptance of some changes but rejects others.

If the modifications raise no concerns to the server admin,
it's accepted without further correspondence.
However some modifications might raise concerns, in which case,
the server admin will likely contact the project admin to verify
they understand the ramifications.

In this role, the server admin relies on their (typically year of) research experience,
as well as familiarity with REDCap mechanisms to avoid problems.

Most of the concerns involve unintentional destruction or corruption of data.

## Large number of records to be deleted before moving to production {#sec-trouble-productionchanges-deleterecords}

### Background {.unnumbered}

When a project is moved to production,
the software will ask the project admin if they want to delete the existing records.
In fact, that's the default selection because it's assumed that the project was
[thoroughly tested](../check/testing.md) during development with fake records,
and now is transitioning to real records.

When reviewing the proposal, the software informs the server admin how many
records will be deleted,
assuming the project admin selected "Delete All Records".
If the server admin sees that 10-20 records will be deleted,
they'll believe this is a reasonable volume of test records
and accept the deletion as the project moves to production.

However, a larger volume like 50+ records might raise concerns that real data might
have been entered.
The server admin will likely email you to confirm all the records should be wiped.
Notice it's not desirable to delete these test records once the project is in production,
because they'll be included in the logs, and could confuse someone later auditing the project.

### Tips to avoid additional correspondence {.unnumbered}

By all means, please create and employ a large volume of records to test.
If you have created a lot of test records and don't want to risk a delay,
you can mass delete them before requesting the move to production.
In the "Other Functionality" tab, click "Erase all data".

### To confirm your intent {.unnumbered}

_If the server admin asks you about this issue..._ :
In your response email, be clear that the large volume of records
are in fact test records that should be discarded.

## Deleting a variable with data {#sec-trouble-productionchanges-deletevariable}

### Background  {.unnumbered}

You've deleted a variable that contains data.

In the review screen, the server admin will a warning like:

> Fields to be DELETED:
>
> * `zip_code` "Zip Code of Residence" (106 records affected)
> * `county` "County of Residence" (98 records affected)

This can raise the server admin's concerns that the project admin meant to delete a different variable,
or is unaware of the benefits of the `@HIDDEN` action tag.

### Best Practices {.unnumbered}

Instead of deleting a variable, consider using the `@HIDDEN` action tag.
Read about its uses in @sec-designint-action-common-hidden.

### To confirm your intent {.unnumbered}

_If the server admin asks you about this issue..._ :
In your response email, be clear that you really want the variable's data erased forever.
And explain why it's not adequate to merely conceal the variable from the user.
