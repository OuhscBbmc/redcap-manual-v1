---
abstract: Design variables to increase data quality and fidelity.

author:
  - name: Lise DeShea
    affiliation: University of Oklahoma Health Sciences
    affiliation-url: https://ouhsc.edu/bbmc/
    email: lise-deshea@ou.edu
    orcid: 0000-0003-3232-5216
    attributes:
      corresponding: true
  - name: Thomas Wilson
    affiliation: University of Oklahoma Health Sciences
    affiliation-url: https://ouhsc.edu/bbmc/
    email: thomas-wilson@ou.edu
    orcid: 0009-0009-1239-1348


csl: ../assets/csl/apa-7e.csl
---

# Variable Decisions {#sec-designbas-variable}

**Chapter Leads**: Lise DeShea & Thomas Wilson

## Variable decisions {#sec-designbas-variable-decisions}

When you are creating and managing a database, many decisions must be made about variables.
A variable is a quantity or property that can take on different values. 
"Name" is a variable.
"Age" is a variable.
These are two kinds of variables. 
Data are stored in variables.
REDCap accepts many kinds of data, including file uploads and signatures.
But you have to tell REDCap what to expect when you create variables.
Further, you need to think about what to name a variable. 
If you named everything "item_1," "item_2," "item_3," etc., whoever analyzes the data
will have a hard time keeping track of what variable is being referenced.
This chapter will lead you through many decisions about variables.

## Variable names {#sec-designbas-variable-variablenames}

The most basic detail to decide about a variable is what to call it: the variable name.
That decision often is tied up in what kind of variable it is.
We will show you how to create a variable inside an existing form in a practice project.
We also will explain the difference between a variable *name* and its *label*. 

We need to go into the Online Designer. 
When you log into REDCap and click on a project name, you will have two ways to get
into Designer. 
One is in the top left corner of your screen, with a link called *Designer*.

![Enter Designer](images/designbas/variables/designer-1.jpg){width=80%}

The other way is on the same screen in the middle of the page with a box labeled *Online Designer*.

![Enter Online Designer](images/designbas/variables/designer-2.jpg){width=80%}

Either way, you end up on the same page, which lists the forms in the project.

![List of forms](images/designbas/variables/forms.jpg){width=80%}

Clicking on any form name will open it.
Form 1 in this project already has five variables in it: the Record ID and four other variables.
The Record ID cannot be deleted.
It is a unique identifier for each record entered in the project.
It can be renamed, but we will leave ours alone. 

## Variable names vs. labels {#sec-designbas-variable-namesvslabels}

To edit a variable, click on the little pencil icon.

![Pencil icon](images/designbas/variables/pencilicon.jpg){width=80%}

We get a new window labeled *Edit Field*.
We can learn several things about this variable from this window.
First, it is a Notes Box (Paragraph Text) field.
That means it could be used to enter a description of a clinic visit, for example.

![Edit Field](images/designbas/variables/editfield.jpg){width=80%}

You see that the large box under *Field Label* is blank.
No label has been created for this variable.
Further, on the right side of the window is the *Variable Name*.
The Field Label is what shows up to the person filling out the form.
The Variable Name is used to store the data inside REDCap.
An analyst will use the variable name.

*variable_1* is a poor name for a variable because an analyst would not know 
anything about the data simply by looking at that variable name.
Let's change it to *visit_note* and add a label to match, then click Save.

![Change variable name](images/designbas/variables/visitnote.jpg){width=80%}

Let's look at *variable_2* and see what kinds of variables can be created.
This variable was created as a *Text Box (Short Text, Number, Date/Time, ...)*.
Let's change it to capture a participant's first name

![Change variable name](images/designbas/variables/name-first.jpg){width=80%}

Note that we did not name the variable first_name.
We recommend starting the variable name with something general, then getting more
specific.
Then the analyst could see all the variables involving someone's name and distinguish among them.
When you are creating variables in REDCap, it's a good idea for you to be
quite familiar with the study, survey, or investigation *before* you start
creating variable names.
If this study collected data for a parent and a child, then *name_first* would be a poor choice.
A better choice might be *name_parent_first.*

![Parent's first name](images/designbas/variables/parent-first-name.jpg){width=80%}

## Types of variables {#sec-designbas-variable-variabletypes}

As mentioned above, REDCap can capture many kinds of data.
Let's look at variable_3 and see what kinds of variables are available.
Next to the words *Field Type* is a drop-down menu of kinds of variables.

![Field type dropdown](images/designbas/variables/kinds-of-variables.jpg){width=80%}

As the creator of a REDCap project, you are on the front line of ensuring data quality.
The specifications you enter for each variable can make a world of difference.
Your specifications can force a data entry person to enter a number with two decimal places
or ensure that an email address is in a valid format.
The specs also can set limits on numbers so a data entry person would not 
accidentally enter that a person was 150 years old, instead of 15.

A *Text Box* field can handle many kinds of data.
Let's look at how to specify which kind of entries will be valid.
Suppose we want the data entry person to enter a child's age for a study
involving only children ages 2 through 8 years.
Further, two children from the same family could be involved in the study.
So we will name the variable to specify we are talking about the first child,
and we will use a setting called *Validation*, which has a drop-down menu beside it.

![Validation settings](images/designbas/variables/validation-1.jpg){width=80%}

You can see a scroll bar on the right side of the drop-down menu.
So there are many validation types from which to choose.
For child's age in years, we will choose Integer.
After we do that, we see options pop up for *Minimum* and *Maximum*.
We will enter the minimum and maximum ages possible for this study.

![Validation range](images/designbas/variables/validation-2.jpg){width=80%}

Now someone entering data who typed an age outside that range will get an error message,
saying that the number is beyond the limits you set.

## Date variables {#sec-designbas-variable-datevariables}

Let's look at one more kind of variable: a date field. We will change variable_4
on our example project to the date of birth for the first child in our study.

![Kinds of date variables](images/designbas/variables/date_birth_child_1.jpg){width=80%}

Date validation can be as general as a date or as specific as the date and time down to the second.
For a birth date, we only need the date. We have 3 format options available to us: day-month-year,
month-day-year, or year-month-day. Keeping with our recommendation of going from general to
specific, we will choose Y-M-D. (This recommendation is in keeping with the International
Organization for Standardization 8601, which you can google. This format eases sorting data
by earliest to latest date.)

## Creating a new variable {#sec-designbas-variable-newvariables}

Our examples so far have involved modifying variables that already existed in a REDCap
project.
Let's create a new variable. Look for the buttons that say "Add Field":

![The Add Field button](images/designbas/variables/add-field.jpg){width=80%}

We can insert a field after any of the existing fields in the project by clicking one
of those buttons. Doing so opens a window called Add New Field. Let's create a field for
the best contact phone number:

![Creating a new variable](images/designbas/variables/phone-contact-1.jpg){width=80%}

We named it phone_contact_1 to indicate it is the best number for contacting the family.
Then we click Save, and the new variable now appears on the form.
Note that we chose Phone (North America) as the Validation standard. Now, if someone enters a
phone number without an area code, an error message will say an invalid number was entered.

We recommend when you are learning about REDCap, request a practice project, then
go into Form 1, which gets created automatically, and play around with creating different
kinds of variables.
A practice project is the best way to learn by doing.
To request a practice project, click on My Projects in the top left corner of the page, 
then click on the link at the top of the next page that says "+ New Project."
Fill out the form and a REDCap administrator will create a "Practice/Just For Fun"
project for you.
You will get an email when the project has been created and is available to you.

![Go to My Projects](images/designbas/variables/my-projects.jpg){width=80%}

![Go to New Project](images/designbas/variables/new-project.jpg){width=80%}

![Request practice project](images/designbas/variables/request-project.jpg){width=80%}


::: {.callout-note appearance="simple"}





## Additional Chapter Details

This chapter was last edited in November 2025.
If you have suggested modifications or additions, please see [How to Contribute](../index.qmd#sec-welcome-contribute) on the book's welcome page.
:::
