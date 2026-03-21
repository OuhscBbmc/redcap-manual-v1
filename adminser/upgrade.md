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
Make sure you select the correct value among these three dimensions:
(i) LTS vs Standard,
(ii) "Update" (as opposed to the "Fresh Installation"), and
(iii) version number.

### Transfer file

Transfer the zipped file from your client machine to the web server,
using a tool like WinSCP.
For this scenario, say it's transferred to the "Downloads" directory
of the "eaglesmith" account.

### Update Web Server

The first component to be upgraded is the PHP code residing on the web server,
so log into the web server.

Decompressed the files and
move them to the appropriate REDCap folder
where they are visible and available to users.

On a Linux distribution like RHEL, the code is:

```bash
# !! This is rough from memory.  I haven't tested it yet. !!
# Unzip the file into a directory.
unzip /usr/eaglesmith/Downloads/redcap_*.zip

# Move the directory to a redcap subdirectory.
mv /usr/eaglesmith/Downloads/redcap_ /var/www/html/redcap
```

### Obtain SQL Update Code

The second component to upgrade is the database,
which involves executing SQL code that
REDCap's installation process provides you.

TODO: replace with the real link:

After moving the PHP code, go to `<redcap-installation>/upgrade.php`,
from your desktop.
The page should indicate that the previous step was successful
and provide SQL code.

Save the code as a sql file,
then transfer the file from your desktop to the database server,
specifically `usr/eaglesmith/redcap-upgrades`.
For the sake of consistency,
use the same approach as you transferred the PHP code to the web server in the previous step.

TODO: add as a foot note
> It may be possible to copy the code from the web page and
> paste it into the database IDE,
> but we prefer the proposed approach for two reasons:
>
> 1. the sql file helps document changes if you need to reconstruct something
> 1. It's tricky moving the code across machines if
>    the linux server-client procotol doesn't support copy-paste operations.

### Update Database Server

Log into the database server and open a database IDE.
Open the new upgrade sql file.
Execute the entire file.

Although the entire file should be executed eventually,
but you can chose either line-by-line or all-at-once.
If it's a small hop between versions and the upgrade went smoothly
on the non-production instance,
consider making your life easier hitting run once.

However if there were previous problems, we recommend a more conservative approach.
Possibly there were problems upgrading the non-production instance.
Or perhaps that ran smoothly, but the production upgrade failed,
so you rolled back to your VM snapshot.
Run small snippets of the code individually.
This incremental approach will help you identify where the code failed,
and therefore be more suggestive how to solve the problem.

TODO: footnote:
> MySQL Workbench is a popular IDE for MariaDB/MySQL databases.
> Our slight preference is DBeaver.

::: {.callout-note appearance="simple"}

#### Database Context

You don't need to learn SQL to upgrade REDCap,
but a little understanding of the process
could help if the process doesn't go smoothly.

All upgrades will involve a least one line of [DML SQL]()
code that adjust configuration values,
like the one that increases `redcap_version`.

More substantial upgrades involve [DDL SQL]()
code that modifies the structure of the database,
like adding a table to support a new feature.
:::

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
