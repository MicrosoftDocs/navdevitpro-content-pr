# navdevitpro-content-pr

Welcome to the repository for the preliminary devitpro content for on-prem &amp; PaaS.

======================================
## Getting started with GitHub
### Set up you account
1. Get a GitHub account.
2. Link it to your work account at [https://opensourcehub.microsoft.com/](https://opensourcehub.microsoft.com/].

### Contributing
You do not have write access to the master repo microsoft/navdevitpro-content-pr. This means that to make changes, you must commit the changes, and then create a pull request to include the changes. A writer (UA) will then review the request and pull the content into the master repo.

There are a few ways to work with the repo:
- You can edit directly in the repo on GitHub.com. 
- You can fork the repo and then create a pull request to include your changes. UA will then pick up the changes as needed. 
- Work locally by downloading the GitHub Desktop application from here: [https://desktop.github.com/](https://desktop.github.com/). This lets you clone the repo on your machine. You can then nake changes, sync with the master repo on Github, and create a Pull Reuest.

### How to contribute
1.  Make changes to an existing file or add a new one.
2.  Commit changes.
3.  Create Pull Request

## Authoring in Markdown
----------------------
### General info:
[Getting started with writing and formatting on GitHub](https://help.github.com/articles/getting-started-with-writing-and-formatting-on-github/)

### Authoting tools:
You can edit on GitHub or use any text editor. Just save the file as a .md type. Here are a couple good tools that provide you with nice features.  
- [Visual Studio Code](https://code.visualstudio.com/)
- [Atom](https://atom.io/)

### Headings
Use ```#``` for headings.

Examples:
```#``` Heading 1, looks like:
# Heading 1

```##``` Heading 2, looks like:
## Heading 2

```###``` Heading 3, looks like:
### Heading 3


### Bulleted lists
Use - to create bullets, for example:

The following options are available:
```
- first option
- second option
- third option
```

### Ordered lists
Use numbers for ordered lists. No space between the lines, we'll let the template take care of that.

```
1. In the **Search** box, enter **Payment Journal**, and then choose the related link.
2. In the **Payment Journal** window, on the first journal line, enter the relevant information about the payment entry.
3. To apply a single vendor ledger entry:
4. In the **Applies-to Doc. No.** field, choose the field to open the **Apply Vendor Entries** window.
```

### Bold and italics syntax
Use ```**bold**``` and ```*italics*```

### Tables
- For tables in the body, use the markdown syntax.

```
| To   | See                       |
|------|---------------------------|
|<text>|<link>|
| | |
| | |
```

- For nested tables in ordered and unordered lists use HTML-syntax. Markdown does not support tables very well. If you use the markdown syntax the list will be broken, the table will align left and list will be renumbered.

### Comment syntax
Useful for sections that are not ready and will not pass the build check.
```
<!-- Comments -->
```
Examples
```
<!-- [Managing Payables](payables-manage-payables.md)-->
<!-- This is a paragraph that spans more lines and I can just put the comment tag
at the beginning and end of it -->
```
### Links
Ordinary link to a different topic in the same folder

These links have the format ```[link text](filename.md)```.

Example:
```[Managing Payables](payables-manage-payables.md)```


### Link to a topic in a subfolder of the source topic

These links have the format ```[link text](subfolder/filename.md)```.

For example, you want to link to payables-manage-payables.md from ui-work-general-journals.md, where the folder structure is as follows:

- articles
    - ui-work-general-journals.md
- ManagePayables
    - conManagePayables.md

Here is the link:
```[Manage Payables](ManagePayables/payables-manage-payables.md)```

### Link to a topic in a different folder than source topic

These links have the format ```[link text](../folder/filename.md)```.

For example, you want to link to payables-manage-payables.md from receivables-manage-receivables.md, where the folder structure is as follows:

- articles
    - ManageReceivables
        - receivables-manage-receivables.md
    - ui-work-general-journals.md
    - ManagePayables
        - payables-manage-payables.md

Here is the link:
```[Manage Payables](../ManagePayables/payables-manage-payables.md)```

### Link to a place in the same article
From within an article, you can create a link to a specific heading in the same article. You can create the link like other links except with the following format:

```[link text](#target-heading)```

target-heading is the text of the heading that you want to link to, except it is all lowercase and spaces between words are replaced with hyphens. For example, here is the link:
```[How Autoscaling Works](#how-autoscaling-works)```

To the heading:
```## How Autoscaling Works```

### Link to a place in a different article
From an article, you can create a link to a specific heading in another article. You can create the link like other links except with the following format:

```[link text](targetarticlename#target-heading)```

targetarticlename is the file name of the article, including the .md file type.
target-heading is the text of the heading that you want to link to, except it is all lowercase and spaces between words are replaced with hyphens.

For example, to link to the heading "How Autoscaling Works" in the article Autoscaling.md", add the following code:
```[link text](Autoscaling.md#how-autoscaling-works)```

### Link to MSDN
Omit the brackets with the NAV version info. Markdown mistakes that bracket for its own link indication.
Example:  
MSDN URL: ```https://msdn.microsoft.com/en-us/library/hh173988(v=nav.80).aspx```  
Entered in markdown: ```https://msdn.microsoft.com/en-us/library/hh173988.aspx```

### Line breaks (soft return)
In the editor, add two blank spaces at the end of the sentence and hit return. This is used in the See Also list. (See Also must be heading 2.)

### Continue steps after a non-step para
Enter four spaces in front of the non-step para. Otherwise, the non-step para will restart the step sequence.

### TOC
The TOC structure of the TOC file is as follows:

```
#[Overview](overview.md)
 ##[Topic 1](topic-1.md)
 ##[Topic 2](topic-2.md)
 ##[Topic 3](topic-3.md)
 ##[Topic 4](topic-4.md)
```

### Standard Phrases
All fields in Project "Madeira" have tooltips. Therefore, do not document fields in Help. To refer readers to the tooltips, use this standard phrase where relevant:    
"Choose a field to read a short description of the field or link to more information."

### File naming

#### Rules
- No spaces or punctuation characters. Use hyphens to separate the words in the file name.
- Use all lowercase letters
- No more than 80 characters - this is a publishing system limit
- Use action verbs that are specific such as develop, buy, build, troubleshoot. No -ing words.
- No small words - don't include a, and, the, in, or, etc.
- Country-specific article file names are prefixed with the country code. Example: "ca-" for Canada.
- All files must be in markdown and use the .md file extension.

#### Examples

|Topic title |Naming  |
|------------|--------|
|How to: Select a Company|ui-how-select-company.md|
|Enter Criteria in Filters|ui-enter-criteria-filters.md|
|Troubleshooting: Record Locked by Another User|ui-troubleshoot-record-locked-another-user.md|
|Changing Role Center|ui-change-role-center.md|
|||
|Set Up Currencies|finance-setup-currencies.md|
|How to: Set Up Purchasers|purchases-how-setup-purchasers.md|
|Understanding Session Timeouts|admin-understand-session-timeouts.md|
|Manage Data Encryption|admin-manage-data-encryption.md|
|||
|Get Project “Madeira” on My Device|mobile-get-madeira-apps.md|
|Get My Project “Madeira” Outlook Add-In|office-get-madeira-outlook-addin.md|
|||
|How to: Work With GIFI Codes in Canada|ca-finance-work-GiFI-codes.md|

Naming consists of the following elements: ```<country prefix>-<category prefix>-<topic title>.<extension>```
