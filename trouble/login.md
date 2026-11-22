---
abstract: Help logging to a REDCap Server

author:
  - name: Thomas Wilson
    affiliation: University of Oklahoma Health Campus
    affiliation-url: https://ouhsc.edu/bbmc/
    email: thomas-wilson@ou.edu.
    orcid: 0009-0009-1239-1348
    attributes:
      corresponding: true

  - name: Will Beasley
    affiliation: University of Oklahoma Health Campus
    affiliation-url: https://ouhsc.edu/bbmc/
    email: wibeasley@hotmail.com
    orcid: 0000-0002-5613-5006

csl: ../assets/csl/apa-7e.csl
---

# Trouble Logging into a REDCap Server {#sec-trouble-login}

**Chapter Leads**: Thomas Wilson

## `ERR_TOO_MANY_REDIRECTS` Error {#sec-trouble-login-toomanyredirects}

::: {.callout-note}

## Problem Description

This problem appears differently, depending on your browser.
But all of the browsers ultimately display `ERR_TOO_MANY_REDIRECTS`.
:::

Suggested Explanation and Solution:

Sometimes the authentication mechanism gets confused if you've logged into different OU or OU Health accounts.
Fortunately there is an easy way to reset the credentials cached in your computer.

* First, visit <https://outlook.office.com> and complete login.  Use your conventional OU credentials.
* Second, visit <https://bbmc.ouhsc.edu/>.  Use your conventional OU credentials again.
