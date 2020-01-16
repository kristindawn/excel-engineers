---
title: "Introduction"
teaching: 5
exercises: 5
questions:
- "What are the components of a spreadsheet?"
- "Why does the type of data I assign matter?"
- "What are some cues that tell me I should check my data?"
objectives:
- "Understand the function of rows, columns, and cells."
- "Know the difference between data types"
- "Identify the cues for errors in Excel."
keypoints:
- "Rows, columns, and cells are distinct elements with different functions."
- "Assigning the correct data type is extremely important."
- "You can't perform certain functions on certain data types."
- "Sometimes Excel misidentifies errors."
---


In this section we will talk about the different parts of a spreadsheet, what makes them different, and how we can use their features to our advantage. 

## Components of a Spreadsheet

While we have probably all used a spreadsheet in Excel for one reason or another, you probably haven't given much thought to the different components of that spreadsheet. We will go through a quick primer to make sure that we are all on the same page.

**Rows** are the horizontal series of data in your spreadsheet. They are indexed with letters, starting at 1. Rows typically store data for one *observation* - the data for one sample that you have run for example. There is usually one piece of information in a row that is unique from the other rows, like a sample number or a part number.

**Columns** are the vertical component of your data. They are indexed with letters. Columns typically have the data for one field or variable for all of the observations - the weight of the samples for example. The headings for the columns should be descriptive and it is helpful if they have the unit of measure. It is not good practice to use the letter as your only way to identify the column, as they can be moved or deleted.

**Cells** are the smallest component of a spreadsheet. A cell represents the value for one variable for one observation. They are represented by the column letter and row number (for example, A1 is the cell in the top left corner of your spreadsheet). 

![Forking Repositories]({{ page.root }}/fig/forking.svg)

However, GitHub only allows a user to have one fork of any particular repo.
This creates a problem for us because an author may be involved in writing several lessons,
each with its own repo.
We therefore use [GitHub Importer][github-importer] to create new lessons.
After the lesson has been created,
we manually add the [template repository]({{ site.template_repo }}) as a remote called `template`
to update the lesson when the template changes.

![Repository Links]({{ page.root }}/fig/repository-links.svg)

## GitHub Pages

If a repository has a branch called `gh-pages` (short for "GitHub Pages"),
GitHub publishes its content to create a website for the repository.
If the repository's URL is `https://github.com/USERNAME/REPOSITORY`,
the website is `https://USERNAME.github.io/REPOSITORY`.

GitHub Pages sites can include static HTML pages,
which are published as-is,
or they can use [Jekyll][jekyll] as described below
to compile HTML and/or Markdown pages with embedded directives
to create the pages for display.

> ## Why Doesn't My Site Appear?
>
> If the root directory of a repository contains a file called `.nojekyll`,
> GitHub will *not* generate a website for that repository's `gh-pages` branch.
{: .callout}

We write lessons in Markdown because it's simple to learn
and isn't tied to any specific language.
(The ReStructured Text format popular in the Python world,
for example,
is a complete unknown to R programmers.)
If authors want to write lessons in something else,
such as [R Markdown][r-markdown],
they must generate HTML or Markdown that [Jekyll][jekyll] can process
and commit that to the repository.
A [later episode]({{ page.root }}/04-formatting/) describes the Markdown we use.

> ## Teaching Tools
>
> We do *not* prescribe what tools instructors should use when actually teaching:
> the [Jupyter Notebook][jupyter],
> [RStudio][rstudio],
> and the good ol' command line are equally welcome up on stage.
> All we specify is the format of the lesson notes.
{: .callout}

## Jekyll

GitHub uses [Jekyll][jekyll] to turn Markdown into HTML.
It looks for text files that begin with a header formatted like this:

~~~
---
variable: value
other_variable: other_value
---
...stuff in the page...
~~~
{: .source}

and inserts the values of those variables into the page when formatting it.
The three dashes that start the header *must* be the first three characters in the file:
even a single space before them will make [Jekyll][jekyll] ignore the file.

The header's content must be formatted as [YAML][yaml],
and may contain Booleans, numbers, character strings, lists, and dictionaries of name/value pairs.
Values from the header are referred to in the page as `page.variable`.
For example,
this page:

~~~
---
name: Science
---
{% raw %}Today we are going to study {{page.name}}.{% endraw %}
~~~
{: .source}

is translated into:

~~~
<html>
  <body>
    <p>Today we are going to study Science.</p>
  </body>
</html>
~~~
{: .html}

> ## Back in the Day...
>
> The previous version of our template did not rely on Jekyll,
> but instead required authors to build HTML on their desktops
> and commit that to the lesson repository's `gh-pages` branch.
> This allowed us to use whatever mix of tools we wanted for creating HTML (e.g., [Pandoc][pandoc]),
> but complicated the common case for the sake of uncommon cases,
> and didn't model the workflow we want learners to use.
{: .callout}

## Configuration

[Jekyll][jekyll] also reads values from a configuration file called `_config.yml`,
which are referred to in pages as `site.variable`.
The [lesson template]({{ site.template_repo }}) does *not* include `_config.yml`,
since each lesson will change some of its value,
which would result in merge collisions each time the lesson was updated from the template.
Instead,
the [template]({{ site.template_repo }}) contains a script called `bin/lesson_initialize.py`
which should be run *once* to create an initial `_config.yml` file
(and a few other files as well).
The author should then edit the values in the top half of the file.

## Collections

If several Markdown files are stored in a directory whose name begins with an underscore,
[Jekyll][jekyll] creates a [collection][jekyll-collection] for them.
We rely on this for both lesson episodes (stored in `_episodes`)
and extra files (stored in `_extras`).
For example,
putting the extra files in `_extras` allows us to populate the "Extras" menu pulldown automatically.
To clarify what will appear where,
we store files that appear directly in the navigation bar
in the root directory of the lesson.
[The next episode]({{ page.root }}/03-organization/) describes these files.

{% include links.md %}


{% include links.md %}

