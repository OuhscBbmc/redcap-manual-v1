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

If the modification raises no concerns of the server admin, then
it's accepted without further correspondence.
However, for a modification that raises concerns,
the server admin will contact the project admin to verify
the ramifications are understood.

In this role, the server admin relies on their (typically years of) research experience,
as well as familiarity with REDCap mechanisms to avoid problems
that are difficult to undo.
Most of the concerns involve unintentional destruction or corruption of data.

## Large number of records to be deleted before moving to production {#sec-trouble-productionchanges-deleterecords}

### Background {.unnumbered}

When a project is moved to production,
the software will ask the project admin if the existing records should be deleted.
In fact deletion is the default selection, because it's assumed that the project was
[thoroughly tested](../check/testing.md) during development with fake records,
and now is transitioning to real records.

When reviewing the proposal, the software informs the server admin how many
records will be deleted,
assuming the project admin selected "Delete All Records".
If the server admin sees that 10-20 records will be deleted,
they'll believe this is a reasonable volume of test records
and accept the deletion as the project moves to production.

However, a larger volume like 50+ records might raise concerns that real data might
have been entered, and now would be lost accidentally.
The server admin will likely email the requester, in order to confirm all the records should be wiped.
Notice it's not desirable to delete these test records once the project is in production,
because the records will be included in the logs, and could confuse someone later auditing the project.

### Tips to avoid additional correspondence {.unnumbered}

By all means, please create and employ a large volume of records to test.
If you have created a lot of test records and don't want to risk a delay,
you can mass delete them before requesting the move to production.
In the "Other Functionality" tab, click "Erase all data".

### To confirm your intent {.unnumbered}

_If the server admin asks you about this issue..._ :
In your response email, be clear that the large volume of records
are in fact test records that should be discarded.

## Deleting a variable {#sec-trouble-productionchanges-deletevariable}

### Background  {.unnumbered}

You've deleted a variable that contains data.

In the review screen, the server admin will see a warning like:

> Fields to be DELETED:
>
> * `zip_code` "Zip Code of Residence" (106 records affected)
> * `county` "County of Residence" (98 records affected)

This can raise concerns that the project admin meant to delete a different variable,
or is unaware of the benefits of the `@HIDDEN` action tag.

### Best Practices {.unnumbered}

Instead of deleting the variable, consider using the `@HIDDEN` action tag.
Read about its uses in @sec-designint-action-common-hidden.

### To confirm your intent {.unnumbered}

_If the server admin asks you about this issue..._ :<br>
In your response email, be clear that you really want the variable's data erased forever.
And explain why it's not adequate merely to conceal the variable from the user.

## Deleting a multiple choice option {#sec-trouble-productionchanges-deletemcoption}

### Background  {.unnumbered}

You've deleted an option (within a multiple choice variable) that contains data.
This scenario is a close relative of @sec-trouble-productionchanges-deletevariable.

This can raise concerns that the project admin meant to delete a different option,
or is unaware of the benefits of the `@HIDECHOICE` action tag.

### Best Practices {.unnumbered}

Instead of deleting the response option, consider using the `@HIDECHOICE` action tag.
Read about its uses in @sec-designint-action-common-hidechoice.

### To confirm your intent {.unnumbered}

_If the server admin asks you about this issue..._ :<br>
In your response email, be clear that you really want the variable option's data erased forever.
And explain why it's not adequate to merely conceal the choice from the user.

## Rewording a multiple choice option {#sec-trouble-productionchanges-rewordmcoption}

### Background  {.unnumbered}

Sometimes multiple choice options need to be reworded during production,
either because additional respondents have found ambiguities undiscovered during the pilot,
or because the real world has changed.

A server admin will quickly approve a change like this, because
it's clear the old wording and new wording are reflecting the same concept.
In other words, it's safe to combine all the old 1s (ie, "mail")
with the new 1s (ie, "male") in the same eventual bucket.

| Old Code | Old Label | New Code | New Label |
|----------|-----------|----------|-----------|
| 1        | mail      | 1        | male      |
| 2        | female    | 2        | female    |

However, this modification will corrupt the variable's data.
In other words, it's _unsafe_ to combine the old 1s (ie, "male")
with the new 1s (ie, "female").
During the analysis, all the respondents answering 1 will be combined,
and the before/male values will be indistinguishable
from the after/female values.

| Old Code | Old Label | New Code | New Label |
|----------|-----------|----------|-----------|
| 1        | male      | 1        | female    |
| 2        | female    | 2        | male      |

### Best Practices {.unnumbered}

If you simply want to reorder the options presented to the user,
then do it.  Just make sure to keep the code-label pair consistent,
like this revision does.
The codes do not need to be sorted in numeric order.
(In fact, the codes don't even need to be numeric.)

| Old Code | Old Label | New Code | New Label |
|----------|-----------|----------|-----------|
| 1        | male      | 2        | female    |
| 2        | female    | 1        | male      |

If the necessary changes are more complex, and involve
rewording, reordering, creating, and/or deleting choices,
then employ a combination of this section
and @sec-trouble-productionchanges-deletemcoption.
