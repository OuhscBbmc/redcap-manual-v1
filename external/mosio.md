---
abstract: Mosio is a leading text messaging software designed primarily for clinical research. 
It helps improve participant engagement and adherence in studies through automated text messages. 
Researchers can use Mosio to send reminders, alerts, and surveys,
making it easier to collect data and keep participants on track.

<!-- You can integrate Mosio into your REDCap project to communicate with participants via text messaging. -->

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

# Mosio {#sec-external-mosio}

## Motivation & Overview {#sec-external-mosio-motivation}

In recent years, many researchers have found that texting is a productive channel for keeping in touch with participants,
either by itself or as a supplement to conventional communication.
[Mosio](https://www.mosio.com/) is a company that develops, supports, and licenses a product called
[REDCap Direct](https://www.mosio.com/redcap/).

The [REDCap Direct](https://www.mosio.com/redcap/) website provides a lot of current information
that we won't try to replicate in this manual.
Instead we'll outline when you might consider it,
and how to ask OU's [Server Administrators](../adminpr/user.md#sec-adminpr-user-role-ocri) for help establishing for your project.

## Pricing {#sec-external-mosio-pricing}

Mosio offers several pricing plans tailored to different needs.  
Outbound messages beyond what is listed below can be purchased at an addition price.
For exact pricing and to get a quote tailored to your specific needs, it's best to contact Mosio directly through their
[website](https://www.mosio.com/).

Here is a list of some of the details:  

### Basic Plan: {#sec-external-mosio-pricing-basic}

* Projects: Up to 4
* Outbound Messages: 1,000 per month

### Plus Plan: {#sec-external-mosio-pricing-plus}

* Projects: Up to 10
* Outbound Messages: 3,000 per month

### Pro Plan: {#sec-external-mosio-pricing-pro}

* Projects: Up to 30
* Outbound Messages: 7,500 per month

## Access {#sec-external-mosio-access}

To connect Mosio with REDCap, follow these steps:

1. Set Up Your REDCap Project:

  * Log into REDCap and create a new project.
  * Define your variables using the Data Dictionary or Online Designer.
  * Design your survey and enable surveys under the 'Project Setup' tab.

1. Mosio Account Setup:

  * Ensure you have a Mosio account.
  * Log into your Mosio dashboard and navigate to the integration settings.
  
1. API Configuration:

  * In REDCap, go to the 'External Modules' section and enable the Mosio module.
  * Enter your Mosio API credentials to link the two platforms.

4. Configure Messaging:

  * Define the messaging parameters within Mosio.
  * Set up various types of messages, such as survey invitations, reminders, and follow-ups

This integration allows you to send automated text messages to participants, improving engagement and data collection. If you need more detailed instructions, you can refer to the Mosio REDCap Direct guide

**Chapter Leads**: Thomas Wilson

::: {.callout-note appearance="simple"}

## Additional Chapter Details

This chapter was started in October 2024.
If you have suggested modifications or additions, please see [How to Contribute](../index.qmd#sec-welcome-contribute) on the book's welcome page.
:::
