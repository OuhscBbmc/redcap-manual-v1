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

**Chapter Leads**: Will Beasley

## Preparation {#sec-adminser-upgrade-prep}

### Release Cadence

For these reasons explained in @sec-adminser-security,
it is vital that REDCap is upgraded soon after versions are released.

Notifications that a new version has been released will appear in
the control center.
So as the server administrator is attending to the TODO list periodically in the day,
they should check for updates as well.

However most regular releases occur Friday afternoons,
so your admin team should schedule time to upgrade the server
during this window.

Allowing for a minimal regiment of testing and validation (say, 15 minutes),
the following procedure should take about 30 minutes per server
after you've performed it a few weeks.
It can be completed faster if you rush,
but we suggest blocking off at least 30 minutes
so you can be more observant and patient if something
doesn't look right.

### Avoid Easy Upgrade Feature

As of February 2026, best practices recommended _not_ using
the "Easy Upgrade" procedure.
See Community Post qqqq for further details.

### Offline vs Online Upgrade

### Version Skipping

#### Little Skips

If you upgrade every week, there won't be much opportunity to skip over versions,
say from 10.2.3 to 10.2.6.
Go ahead and make a small jump like this,
especially if the versions were released quickly in succession to address bugs.

#### Big Hops

However if your installation is months behind, say from 10.2.3 to 12.4.2,
the chance of an unhappy upgrade increases.
Not only is more PHP code changing,
which is interacting with external components like LDAP or FHIR,
but the MariaDB database structure is changing more too.

So given the larger risks of big hops we recommend:

1. Upgrading and validating the non-production instances first.
1. Taking the production instance offline.
1. Upgrading only ~3 months of versions at a time.
1. Snapshotting before each jump (and don't delete them until the entire upgrade process is complete)
1. Validating after each jump.

## Snapshot VM {#sec-adminser-snapshot}

In addition to any MariaDB-level backup,
we recommend taking a snapshot immediately before upgrading.
This should involve a snapshot of both
the database server and the web server.

For cost and performance considerations,
we typically retain only the most recent snapshot of each server.

## Steps

### Download

Log into the REDCap Community site and download the latest version.
Make sure you select the correct


### Install

### Delete Previous Versions

### Test and Validate

### Clean Up

## Test and Production Instances

The steps above pertain to updating a single instance of REDCap.
In addition to your _production_ instance,
we strongly suggest you host a _test_ or _development_ too.
If so, perform these steps on the non production server
and verify things operate correct
to minimize the chance the research will be disrupted
when you upgrade the production instance.

TODO: add footnote

> The distinction between a test instance and development instance
> is important to some aspects of server administration,
> but not to this aspect.
> Update all the nonproduction servers you have before your production servers.

::: {.callout-note appearance="simple"}

## Additional Chapter Details

This chapter was started in March 2026.
If you have suggested modifications or additions, please see [How to Contribute](../index.qmd#sec-welcome-contribute) on the book's welcome page.
:::
