---
abstract: Upgrade REDCap Version

author:
  - name: Will Beasley
    affiliation: University of Oklahoma Health Campus
    affiliation-url: https://ouhsc.edu/bbmc/
    email: wibeasley@hotmail.com
    orcid: 0000-0002-5613-5006
    attributes:
      corresponding: true

csl: ../assets/csl/apa-7e.csl
---

# Upgrade REDCap Version {#sec-adminser-upgrade}

## Preparation {#sec-adminser-upgrade-prep}

For these reasons explained in @sec-adminser-security,
it is vital that REDCap is upgraded soon after versions are released.

## Snapshot VM {#sec-adminser-snapshot}

In addition to any MariaDB-level backup,
we recommend taking a snapshot immediately before upgrading.
This should involve a snapshot of both
the database server and the web server.

For cost and performance considerations,
we typically retain only the most recent snapshot of each server.

## Download

## Install

## Delete Previous Versions

## Test and Validate

## Clean Up

**Chapter Leads**: Will Beasley

::: {.callout-note appearance="simple"}

## Additional Chapter Details

This chapter was started in March 2026.
If you have suggested modifications or additions, please see [How to Contribute](../index.qmd#sec-welcome-contribute) on the book's welcome page.
:::
