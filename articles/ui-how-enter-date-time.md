<properties
                pageTitle="How to:Enter Dates and Time | Dynamics NAV"
                description="Describes how to enter dates and time."
                services=""
                documentationCenter=""
                authors="edupont04"/>
<tags
    ms.prod="dynamics-nav-2017"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="na"
    ms.date="07/19/2016"
    ms.author="edupont04" />

# How to:Enter Dates and Time
You can enter dates and times in all the fields that are specifically assigned to dates \(date fields, time fields and datetime fields\).

How you enter dates depends on the culture settings Dynamics NAV is operating under. In the Windows client, the culture settings are determined by the selection made in the Regional and Language Options window in the Control Panel. In the Web client, the culture settings are determined by the Locale ID selected in the User Personalization of the signed in user. For date patterns involving words, the culture of the Dynamics NAV server installation also plays a role, as this determines the language.

The following sections describe how you can enter dates, times, datetimes, durations, date ranges, and how you use date formulas.

## Entering Dates
In a date field you can enter a date using the standard format of the culture your client is using. It does not matter which date separators you use, but they must not contain spaces unless these are the culture's default date separators.

Alternatively, you can use any of the date formats defined by Dynamics NAV. These are described below.

### Current workdate
The word for 'workdate' in the language used by Dynamics NAV, will be evaluated to the currently set work date. Any part from the start of the word can be entered, such as 'w' or 'work'.

To define the work date, On the **Application** menu, choose **Set Work Date**. If you do not define a work date, the system date will be used as the work date. You may want to use a work date if you have many transactions with a date other than today's date.

### Today
The word for 'today' in the language used by Dynamics NAV, will be evaluated to the current date on the client. Any part from the start of the word can be entered, such as 't' or 'tod', as long as it is not also the start of the word 'workdate'.

### Day\-week\-year pattern
You can enter a date as a weekday followed by a week number and, optionally, a year. For example, Mon25 or mon25 means Monday in week 25. If you do not enter a year, the year of the work date is used.

Any part of the start of the word for a day of the week in the Dynamics NAV language can be used. In case of conflicts (such as 's' which could be Saturday or Sunday), the days are evaluated in the order of the client culture. The input is first evaluated against 'workdate' and 'today' as well, so keep this in mind when abbreviating. For example, 't' already means today, so it cannot mean Tuesday or Thursday.

The week number scheme is always ISO 8601, where week 1 is the week with 4 January in it, or the week with the first Thirsday of the year.

### Digit patterns
In a date field you can enter two, four, six, or eight digits:

-   If you enter only two digits, this is interpreted as the day, and it will add the month and the year of the work date.

-   If you enter four digits, this is interpreted as the day and the month, and it will add the year of the work date. The order of the day and month is determined by the client culture. Even if the client culture should have the year before the day and month, four digits are interpreted as the day and month.

-   If the date you want to enter is in the range 01\/01\/1930 through 12\/31\/2029, you can enter the year with two digits; otherwise, enter the year with four digits.

### Closing Date
When you close a fiscal year, you can use closing dates to indicate that an entry is a closing entry. A closing date technically is between two dates, for example between Dec 31 and Jan 1.

To specify that a date is a closing date, put C just before the date: C123101. This can be used in combination with all the date patterns.

### Examples
The following table contains examples of dates using all the formats. It assumes a culture which formats dates year.month.day., a week starting on Monday and English language.

|**Entry**      |**Interpretation**      |
|---------------|------------------------|
|2002.12.31.|2002.12.31.|
|021231|2002.12.31.|
|2.12.31|2002.12.31.|
|02.12.31.|2002.12.31.|
|20021231|2002.12.31.|
|02/12,31|2002.12.31.|
|11|work date year.work date month.11.|
|1112|work date year.11.12.|
|t or today|today's date|
|w or workdate|the working date|
|m or Monday|Monday of the work date week|
|tu or Tuesday|Tuesday of the work date week|
|s or Saturday|Saturday of the work date week|
|su or Sunday|Sunday of the work date week|
|t23|Tuesday of week 23 of the work date year|
|t 23|Tuesday of week 23 of the work date year|
|t\-1|Tuesday of week 1 of the work date year|

## Entering Times
When you enter times, you can insert any non space separators that you want between the units, but if you use double digits for each unit up to milliseconds, then it is not required.

You only have to write the largest units you require; the rest will be set to zero. You can also leave out any AM\/PM indicator.

The following table lists the various ways in which times can be entered and how they are interpreted. This table assumes a culture with AM and PM indicators 'AM' and 'PM', respectively.

|**Entry**      |**Interpretation**      |
|---------------|------------------------|
|05:23:17|05:23:17|
|5|05:00:00|
|5AM|05:00:00|
|5P|17:00:00|
|12|12:00:00|
|12A|00:00:00|
|12P|12:00:00|
|17|17:00:00|
|5:30|05:30:00|
|0530|05:30:00|
|5:30:5|05:30:05|
|053005|05:30:05|
|5:30:5,50|05:30:05.5|
|053005050|05:30:05.05|

Please note that milliseconds are interpreted as decimal notation: 3, 30 and 300 all mean 300 milliseconds, while 03 means 30 and 003 means 3 milliseconds.

You cannot use 24:00 to mean midnight, or any value higher than this.

The word for 'time' in the language used by Dynamics NAV, will be evaluated to the current time on the client. Any part from the start of the word can be entered, such as 't' or 'TIM'.

## Entering Datetimes
When you enter datetimes you must enter a space between the date and the time. The date part can only contain spaces in the form of the official date separator of the client culture. The time can contain spaces around the AM\/PM indicator.

It is also possible to enter only a date in a datetime field, but it is not possible to enter only a time.

The following table lists some examples of date\/time combinations. The example culture has dates in day\-month\-year order, AM\/PM designators, English language and the week starts on Sunday.

|**Entry**      |**Interpretation**      |
|---------------|------------------------|
|08\-01\-2016 05:48:12 PM|08\-01\-2016 05:48:12 PM|
|131202 132455|13\-12\-2002 13:24:55|
|1\-12\-02 10|01\-12\-2002 10:00:00|
|1.12.02 5|01\-12\-2002 05:00:00|
|1.12.02|01\-12\-2002 00:00:00|
|11 12|11\-work date month\-work date year 12:00:00|
|1112 12|11\-12\-work date year 12:00:00|
|t or today|today's date 00:00:00|
|t 10:30|today's date 10:30:00|
|t 3:3:3|today's date 03:03:03|
|w or workdate|the working date 00:00:00|
|m or Monday|Monday of the work date week 00:00:00|
|tu or Tuesday|Tuesday of the work date week 00:00:00|
|sa or Saturday|Saturday of the work date week 00:00:00|
|s or Sunday|Sunday of the work date week 00:00:00|
|tu 10:30|Tuesday of the work date week 10:30:00|
|tu 3:3:3|Tuesday of the work date week 03:03:03|
|t23 t|Tuesday of week 23 of the work date year, current time of day|
|t23|Tuesday of week 23 of the work date year|
|t 23|Today 23:00:00|
|t\-1|Tuesday of week 1 of the work date year|

## Entering Duration
You enter a duration as a number followed by its unit of measure.

Here are some examples.

|**Duration**|**Unit of measure**|
|------------|-------------------|
|2h|2 hrs|
|6h 30 m|6 hrs 30 mins|
|6.5h|6 hrs 30 mins|
|90m|1 hr 30 mins|
|2d 6h 30m|2 days 6 hrs 30 mins|
|2d 6h 30m 56s 600ms|2 days 6 hrs 30 mins 56 secs 600 msecs|

You can also enter a number and it is automatically converted to a duration. The number you enter is converted according to the default unit of measure that has been specified for the duration field.

To see what unit of measure is being used in a duration field, enter a number and see which unit of measure it is converted to.

The number 5 is converted to 5 hrs, if the unit of measure is hours.

##  <a name="BKMK_SettingDateRanges"></a> Setting Ranges
You can set filters on dates, times and datetimes containing a start value and optionally an end value to display only the data contained in that range. The standard rules apply to the way you set date ranges.

|**Meaning**|**Sample expression (Date)**|**Entries included**|
|-----------|---------------------|--------------------|
|**Equal to**|12 15 00|Only those posted on 12 15 00.|
|**Interval**|12 15 00..01 15 01<br /><br /> ..12 15 00|Those posted on dates between and including 12 15 00 and 01 15 01.<br /><br /> Those posted on 12 15 00 or earlier.|
|**Either\/or**|12 15 00&#124;12 16 00|Those posted on either 12 15 00 or 12 16 00. If there are entries posted on both days, they will all be displayed.|
|**Combination**12 15 00&#124;12 01 00..12 10 00<br /><br />..12 14 00&#124;12 30 00..|Entries posted either on 12 15 00 or on dates between and including 12 01 00 and 12 10 00.<br /><br />Entries posted on 12 14 00 or earlier, or entries posted on 12 30 00 or later \- that is, all entries except those posted on dates between and including 12 15 00 and 12 29 00.|

You can use any of the valid formats in date range filters. For example, 'mon14 3..t 4p' applied on a datetime field results in a filter from 3 AM on Monday in week 14 of the current work date year, inclusive, until today at 4PM, inclusive.

## Using Date Formulas
A date formula is a short, abbreviated combination of letters and numbers that specifies how to calculate dates. You can enter date formulas in various date calculation fields and in recurring frequency fields in recurring journals.

> [!NOTE]
>  In all data formula fields, one day is automatically included to cover today as the day when the period starts. Accordingly, if you enter 1W, for example, then the period is actually eight days because today is included. To specify a period of seven days \(one true week\) including the period starting date, then you must enter 6D or 1W\-1D.

Here are some examples of how date formulas can be used:

-   The date formula in the recurring frequency field in recurring journals determines how often the entry on the journal line will be posted.

-   The date formula in the Grace Period field for a specified reminder level determines the period of time that must pass from the due date \(or from the date of the previous reminder\) before a reminder will be created.

-   The date formula in the Due Date Calculation field determines how to calculate the due date on the reminder.

The date calculation formula can contain a maximum of 20 characters, both numbers and letters. You can use the following letters, which are abbreviations for time specifications.

| | |
|-|-|
|C|Current|
|D|Day\(s\)|
|W|Week\(s\)|
|M|Month\(s\)|
|Q|Quarter\(s\)|
|Y|Year\(s\)|

You can construct a date formula in three ways.

The following example shows how current plus a time unit.

| | |
|-|-|
|CW|Current week|
|CM|Current month|

The following example shows how a number and a time unit. A number cannot be larger than 9999.

| | |
|-|-|
|10D|10 days from today|
|2W|2 weeks from today|

The following example shows how a time unit and a number.

| | |
|-|-|
|D10|The next 10th day of a month|
|WD4|The next 4th day of a week \(Thursday\)|

The following example shows how you can combine these three forms as needed.

| | |
|-|-|
|CM\+10D|Current month \+ 10 days|

The following example shows how you can use a minus sign to indicate a date in the past.

| | |
|-|-|
|\-1Y|1 year ago from today|

> [!CAUTION]
>  If the location uses a base calendar, then the date formula that you enter in, for example, the **\($ T\_36\_5792 Shipping Time $\)** field is interpreted according to the calendar working days. For example, a 1W means seven working days. For more information, see [\($ N\_7600 Base Calendar Card $\)](../Topic/\($%20N_7600%20Base%20Calendar%20Card%20$\).md).

## See Also
<!-- [Working with \($ P\_1 Product Name $\)](../Topic/Working%20with%20\($%20P_1%20Product%20Name%20$\).md)
[\($ T\_36\_5792 Shipping Time $\)](../Topic/\($%20T_36_5792%20Shipping%20Time%20$\).md) -->
