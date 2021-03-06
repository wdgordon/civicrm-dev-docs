# Documentation style guide

All CiviCRM guides *(like this Developer Guide)* are intended to provide
high-quality "finished" [documentation] (documentation.md)
about CiviCRM. This Style Guide page documents the standards we wish to
uphold to ensure all guides maintain this high level of quality.

## Parts, chapters, sections

Similar to most text books and manuals, we divide our guides into "parts",
"chapters", and "sections". In mkdocs, these blocks translate as follows:

-   "part" - folder
-   "chapter" - file (in markdown), also one web page with a given URL
-   "section" - heading within the page

In the navigation menu (as stored in `mkdocs.yml`):

-   Keep the page hierarchy to the depth described above
    (i.e. do not put folders within other folders).
-   Each chapter name should be short enough to fit nicely in the menu,
    but also long enough to stand on its own to a reasonable extent.
    The titles set here are used in the navigation menu *and* the page title
    that displays in the browser tab. The guide will be more usable if the
    reader sees two tabs titled "Using Hooks" and "API Usage" instead of
    "Usage" and "Usage".

Each chapter should start with a paragraph that explains what will be
covered in the chapter.

Effort should be given to arrange all content within a guide so that skills and
concepts which build upon one another are presented sequentially.
Although guides should not require start-to-finish reading, providing the
option (when possible) is helpful to some readers.

Don't use terms like "previous chapter", etc. because we may add or re-arrange
chapters in the future. Instead, use a hyperlink to the chapter.

### Headings

The first heading in a chapter should be Heading 1. All others should be
in H2 and H3, only where necessary.  If you find yourself wanting to use
H4, consider if it's truly necessary and whether the chapter should
instead be refactored.

### Capitalization

Titles for parts, chapters, and sections should all be in sentence case
(first word capitalized), not headline case (each word capitalized).

## Formatting conventions

### Describing the CiviCRM user interface

Menu selections, buttons, tabs (basically, things that the reader is
being told to click) should be in bold.

-   Navigate to **Administer > CiviEvent > Event Types** to review the
    default list of event types.
-   Modify event type labels by clicking **Edit** on any row.
-   Click **Add Event Type** to create a new category for your events.

Elements of the system and interface should be capitalized (e.g., the
Events component, the Template Title field).

It is also sometimes helpful for clarity when discussing concepts to use
capitalization to distinguish between a specific activity within CiviCRM
and a generic activity (e.g., the Send Email activity versus sending an
email). However, sometimes it is too cumbersome or just plain weird to
capitalize every instance of a term even if it refers to a specific CiviCRM
thing or technical definition (e.g., scheduled reminders, plain text).
Use your best judgment as to what serves the reader; trying to enforce
consistency in this arena will slow us down or drive us crazy.

Quotes should be avoided as much as possible; however, do use them when
they seem necessary for clarity (e.g., if you are talking about setting
or field labels that are long phrases).

You can divide the CiviCRM interface into administration pages and
public-facing pages.

### Bullets and numbered lists

Bulleted lists should be used to convey short snippets of information.
Numbered lists should be used to describe specific steps in a process
that must be done in order.

Numbered lists should always be made up of full sentences (since they
are instructions) and thus should include terminal punctuation.

Bulleted lists may or may not need to be full sentences. Full sentence
bullets need terminal punctuation. Bullets that are not full sentences
should not have terminal punctuation. However, if any particular list
contains one or more full-sentence bullets, all bullets (even those that
are not full sentences) should have terminal punctuation.

Sections that are over 50% bullets look really bad and not like a book.
If you see a section which is 'all bullets', consider rewriting it
removing them.

### Images

Images should be in png format and a maximum of 690px wide. Please use
descriptive names for images.

Alternative Text  (ALT Tags) should be included for every image.

### Machine-readable symbols

Machine-readable symbols (e.g. files names, classes, functions, variables, database tables, database columns, commands, etc.) should be formatted either with inline monospace or preformatted code blocks (also in monospace). See the [markdown syntax](/markdownrules/#code) to use for such formatting.

### URLs

Sample links to specific CiviCRM URL paths should use `example.org` as the
domain.

```text
http://example.org/civicrm/mailing/queue&reset=1
```

## Language

### Spelling and punctuation

Both U.K. and U.S. English spellings are acceptable; we actually welcome
inconsistency around this. CiviCRM is an international project, so its
mixing it up is a benefit.

Double quotes are preferred over single quotes.

Avoid abbreviations. For example, write "organisation" instead of "org".

Below are our preferred spellings of CiviCRM-specific words:

-   "autoresponder" *(not auto-responder)*
-   "CiviCRM" *(not "Civi")*
-   "deduplicate", "dedupe" *(not "de-duplicate" or "de-dupe")*
-   "dropdown", "dropdown menu" *(not "drop-down")*
-   "meetup" (noun)
-   "non-profit" *(not "nonprofit")*
-   "set up" (verb), "set-up" (noun)
-   "unsubscribe" *(not "un-subscribe")*

### Terminology

-   **contact** - a contact record within CiviCRM
-   **organisation/organization** - a non-profit (or other community group,
    etc) who is (or could be) using CiviCRM
-   **user** - a person who interacts with CiviCRM via the front end
-   **site admin** - a staff member (of an organisation) who regularly
    administers CiviCRM from the front end. (By definition these people are
    also "users".)
-   **system administrator** - a technical person who administers CiviCRM from
    the back end
-   **hosting provider**
    -   In the User Guide - synonymous with *"system administrator"*
    -   In other guides - a person or company that owns and/or maintains the
        server upon which CiviCRM runs
-   **developer** - a computer programmer who writes code to improve or extend
    the functionality, stability, or security of CiviCRM
-   **core team**
    -   In the User Guide - *should be avoided. Use "CiviCRM" or "the CiviCRM
        community".*
    -   In other guides - refers to the
        [core team](https://civicrm.org/teams/core-team)

### Gender neutrality

When describing people in examples, avoid using pronouns that assign specific
genders to them.

Example of gendered language to avoid:

> *When a supporter wishes to fundraise on behalf of an organization, **he** can
> create a fundraising page **himself**, called a Personal Campaign Page, and
> then solicit donations from **his** friends and family. After a donation
> arrives, CiviCRM can even send **him** a notification email.*

Option 1 - fix by using [singular they] *(which is
[rapidly](https://www.washingtonpost.com/news/wonk/wp/2016/01/08/donald-trump-may-win-this-years-word-of-the-year/)
[gaining](http://www.americandialect.org/2015-word-of-the-year-is-singular-they)
[popularity](http://www.npr.org/2016/01/13/462906419/everyone-uses-singular-they-whether-they-realize-it-or-not)
)*:

> *When a supporter wishes to fundraise on behalf of an organization, **they**
> can create a fundraising page **themself**, called a Personal Campaign Page,
> and then solicit donations from **their** friends and family. After a donation
> arrives, CiviCRM can even send **them** a notification email.*

Option 2 - fix by avoiding pronouns entirely:

> *A supporter wishing to fundraise on behalf of an organization can
> autonomously create a fundraising page, called a Personal Campaign Page, and
> then solicit donations from friends and family. After a donation arrives,
> CiviCRM can even send **the supporter** a notification email.*

Avoid fixing gendered language by replacing "he" with phrases such as:
"he/she", "he or she", "she", or "s/he". Such replacements (a) become more
awkward when sentences include multiple pronouns, (b) do not intuitively offer
a consistent choice among them, and (c) fail to acknowledge that some people
identify with genders outside of a binary framework.

[singular they]: https://en.wikipedia.org/wiki/Singular_they

### Tone and vocabulary

Try to avoid constructions that tell people what they *should* do when multiple
options exists. We want to recognize and respect that there is more than one
way to approach being a user or developer. Preferring constructions that
suggest ways that people can do things. We would like to to avoid language that
gets proscriptive or feels intimidating from a reader's perspective, and we
like having a guide that can be consumed by people in different ways.

**For the User Guide only:** We try and limit the
content to tasks that the user can perform from the front end. This means that
we don't go into detailed steps about installation or system administration
tasks.  We do however let people know that there are system administrator tasks
out there (setting up an SSL certificate, configuring CiviMail etc.) and point
them in the right direction when they want to know about those tasks.



