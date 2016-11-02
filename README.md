# navdevitpro-content-pr

Welcome to the repository for the developer and itpro content for on-prem &amp; PaaS.

All articles are stored as Markdown files (.md type) in the **dynamics-nav** folder. they publish to MSDN staging here: https://msdnstage.redmond.corp.microsoft.com/en-us/../how-to--publish-and-install-an-extension?branch=master. 

======================================
## Getting started with GitHub
### Set up your account
1. Get a GitHub account.
2. Link it to your work account at https://opensourcehub.microsoft.com.

### Contributing
You do not have write access to the master repo microsoft/navdevitpro-content-pr. Any changes that you make will go through UA first. This means that to make changes, you must commit the changes, and then create a pull request to include the changes. A writer (UA) will then review the pull request and pull the content into the master repo.

There are a few ways to work with the repo:
- You can edit directly in the Microsoft/navdevitpro-content-pr repo on GitHub.com.

    This is the quickest way and is good for tech-review and small edits.
- You can fork the repo and then work in the fork.

    When you are done in the fork you commit your changes and make a pull request to the master repo. UA will then pick up the changes as needed. This method is good for making changes to existing articles or creating new articles when you cannot get your changes done right away and you want to save them as a work in progress.
- Work locally by downloading the GitHub Desktop application from here: [https://desktop.github.com/](https://desktop.github.com/).

    This lets you clone the repo on your machine. You can then make changes, sync with the master repo on Github, and create a Pull Request. This is useful for working on new content that stretches over a few sessions. This is how UA works.

### Contribution process
The general flow is as follows:

1. Make changes to an existing file or add a new one.
2. Commit proposed changes.
3. Create Pull Request to have the changes included in the master repo.

### How to modify an article directly in the repo on GitHub
1. Open the **articles** folder.
2. Double-click the .md file you want to review/edit.
3. In the tool bar, choose the **Edit this file** (pencil) icon.
3. Make changes. Note: If you want to add a comment, the use the syntax <!-- this is my comment -->
4. When done, choose **Propose file changes** button at the bottom.
5. Choose Create New Pull Request, and then Create Pull Request to send a request for your changes to be included in the master. UA will review the changes.

## Authoring in Markdown

The content is styled using a Markdown syntax as described below. You don't have to worry too much about the Markdown syntax, because it will go through UA.

### General info:
[Getting started with writing and formatting on GitHub](https://help.github.com/articles/getting-started-with-writing-and-formatting-on-github/)

### Authoring tools:
If you want to work locally, you can edit using any text editor. Just save the file as a .md type. Here are a couple good tools that provide you with some nice features, such as Preview.  
- [Visual Studio Code](https://code.visualstudio.com/)
- [Atom](https://atom.io/) (this has spell check and is good for managing many files)

### Properties
Each topic must contain YAML section at the top of the file with the following information:
```
---
title: "A Topic"
ms.custom: na
ms.date: 08/19/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 143a477f-63a9-4a95-b6b0-b4b4dfec5a61
caps.latest.revision: 9
manager: edupont
---
```

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
- For tables in the body, use the Markdown syntax.

```
| To   | See                       |
|------|---------------------------|
|<text>|<link>|
| | |
| | |
```

- For nested tables in ordered and unordered lists use HTML-syntax. Markdown does not support tables very well. If you use the Markdown syntax the list will be broken, the table will align left and list will be renumbered.

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
Entered in Markdown: ```https://msdn.microsoft.com/en-us/library/hh173988.aspx```

### Line breaks (soft return)
In the editor, add two blank spaces at the end of the sentence and hit return. This is used in the See Also list. (See Also must be heading 2.)

### Continue steps after a non-step para
Enter four spaces in front of the non-step para. Otherwise, the non-step para will restart the step sequence.

### Images
1. Save the image as a .png file to the /images folder.
2. Add the image to the content by using the follwoing syntax:

   ```
    ![Descriptive name](http://../images/filename)
   ```

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
The UI has tooltips for getting unblocked. Therefore, do not document fields in Help. To refer readers to the tooltips, use this standard phrase where relevant:    
"Choose a field to read a short description of the field or link to more information."

### File naming

#### Rules
- No spaces or punctuation characters. Use hyphens to separate the words in the file name.
- Use all lowercase letters
- No more than 80 characters - this is a publishing system limit
- Use action verbs that are specific such as develop, buy, build, troubleshoot. No -ing words.
- No small words - don't include a, and, the, in, or, etc.
- Country-specific article file names are prefixed with the country code. Example: "ca-" for Canada.
- All files must be in Markdown and use the .md file extension.

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

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
