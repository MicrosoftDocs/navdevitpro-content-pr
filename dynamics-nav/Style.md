---
title: "Style Guide"
ms.custom: na
ms.date: 02/08/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 31a1fbeb-a4b4-452d-8cf4-4937c0f87479
caps.latest.revision: 4
author: jswymer
---
# Style Guide
Control add-ins for Dynamics 365 "Tenerife" extend a business solution by surfacing contextual functionality alongside business data. Control add-ins empower users to get more done without costly context switching, no matter which device they access Dynamics 365 from. Typical uses of control add-ins include unique data visualizations, surfacing controls from a third party service, or displaying related content from another data source.

Apart from the functionality, an important part of creating a control add-in is making sure the control add-in looks good and blends seamlessly into Dynamics 365 "Tenerife". To achieve this, you should follow these basic principles:

- Apply similar patterns for command, navigation and presentation of data.
- Favor content over chrome
- Design for all platforms and input methods.
- Make it accessible to all users.
- Make it enjoyable and keep users in control.

This article offers a variety of stylistic definitions that can be applied to your AddIn and help you create an experience that delights users and complements Dynamics 365.

> [!IMPORTANT]  
> This article is currently in progress and contents will change.

## Colors
Choosing the right color gives the interface visual continuity. Color can be used to convey information to users, indicate interactivity, give feedback, and more. The following sections describe the colors used Dynamics 365 "Tenerife".


### Main colors
|  Color  |  Name  |  Use  |  HEX value  |
|---------|--------|-------|-------------|
|![Primary (#00B7C3)](media/style/00B7C3.png "Primary (#00B7C3)")|Primary color|Titles, subtitles, and captions.|#00B7C3|
| ![Secondary (#505C6D)](media/style/505C6D.png "Secondary (#505C6D)")|Secondary| Background and links.|#505C6D|
 


<!--
<blockquote STYLE="background-color:#00B7C3;border-left:None;color: white;"><br />Primary (#00B7C3)<br /><br /></blockquote>
<blockquote STYLE="background-color:#505C6D;border-left:None;color: white;"><br />Secondary (#505C6D)<br /><br /></blockquote>

-->

### Accent colors

The following colors are used to accentuate conditions and user activity in the UI. For example, these colors are used as sentinaments, or color indication, on Cues.
  
|  Color  |  Description  | HEX value|
|---------|---------------|----------|
|![Standard (#00B7C3)](media/style/212121.png "Accent (#00B7C3)")|Standard|#212121|
|![Accent (#00B7C3)](media/style/00B7C3.png "Accent (#00B7C3)")|Accent|#00B7C3|
|![Strong (#00B7C3)](media/style/212121.png "Strong (#00B7C3)")|Strong|#212121|
|![Favorable (#35AB22)](media/style/35AB22.png "Favorable (#35AB22)")|Favorable|#35AB22|
|![Ambiguous (#9F9700)](media/style/9F9700.png "Ambiguous (#9F9700)")|Ambiguous|#9F9700|
|![Unfavorable (#EB6965)](media/style/EB6965.png "Unfavorable (#EB6965)")|Unfavorable|#EB6965|
|![Attention (#EB6965)](media/style/EB6965.png "Attention (#EB6965)")|Attention|#EB6965|
|![Subordinate (#A7ADB6)](media/style/A7ADB6.png "Subordinate (#A7ADB6)")|Subordinate|#A7ADB6|

<!--
<blockquote STYLE="background-color: #212121;border-left:None;color: white"><br />STANDARD (#212121)<br /><br /></blockquote>
<blockquote STYLE="background-color: #00B7C3;border-left:None;color: white"><br />ACCENT (#00B7C3)<br /><br /></blockquote>
<blockquote STYLE="background-color: #212121;border-left:None;color: white"><br />STRONG (#212121)<br /><br /></blockquote>
<blockquote STYLE="background-color: #35AB22;border-left:None;color: white"><br />FAVORABLE (#35AB22)<br /><br /></blockquote>
<blockquote STYLE="background-color: #9F9700;border-left:None;color: white"><br />AMBIGUOUS (#9F9700)<br /><br /></blockquote>
<blockquote STYLE="background-color: #EB6965;border-left:None;color: white"><br />UNFAVORABLE (#EB6965)<br /><br /></blockquote>
<blockquote STYLE="background-color: #EB6965;border-left:None;color: white"><br />ATTENTION (#EB6965)<br /><br /></blockquote>
<blockquote STYLE="background-color: #A7ADB6;border-left:None;color: white"><br />SUBORDINATE (#A7ADB6)<br /><br /></blockquote>
-->



<!--
<table style="width:100%;text-align:left;color:white;padding: 10px">
  <tr align="left">
    <th >Name</th>
    <th>HEX</th> 
    <th>RGB</th>
   </tr>
  <tr STYLE="background-color: #FFFFFF;border-left:None;color:black">
    <th>White</th>
    <th>#FFFFFF</th> 
    <th>255, 255, 255</th>
   </tr>
  <tr STYLE="background-color: #000000;border-left:None;color: white">
    <th>Black</th>
    <th>#000000</th> 
    <th>0, 0, 0</th>
   </tr>
</table> 
-->

### More palette colors
|  Color  |  Description  | HEX value|
|---------|---------------|----------|
|![YELLOW (#C9C472)](media/style/C9C472.png "YELLOW (#C9C472)")|Yellow|#C9C472|
|![GREEN (#88CE81)](media/style/88CE81.png "GREEN (#88CE81)")|Green|#88CE81|
|![RED (#E97768)](media/style/E97768.png "RED (#E97768)")|Red|#E97768|
|![BLUE (#75B5E7)](media/style/75B5E7.png "BLUE (#75B5E7)")|Blue|#75B5E7|
|![LIGHTGREEN (#59CCB4)](media/style/59CCB4.png "LIGHTGREEN (#59CCB4)")|Light green|#59CCB4|
|![SKY (#75D8E7)](media/style/75D8E7.png "SKY (#75D8E7)")|Sky|75D8E7|
|![EGG (#EEEA86)](media/style/EEEA86.png "EGG (#EEEA86)")|Egg|EEEA86|
|![ORANGE (#E89E63)](media/style/E89E63.png "ORANGE (#E89E63)")|Orange|#E89E63|
|![VIOLET (#DBBDEB)](media/style/DBBDEB.png "VIOLET (#DBBDEB)")|Violet|#DBBDEB|
|![TEAL (#39B294)](media/style/39B294.png "TEAL (#39B294)")|Teal|#39B294|
|![GRASS (#73BA5A)](media/style/73BA5A.png "GRASS (#73BA5A)")|Grass|#73BA5A|
|![SCARLET (#E65E6D)](media/style/E65E6D.png "SCARLET (#E65E6D)")|Scarlet|#E65E6D|



<!--
<blockquote STYLE="background-color: #C9C472;border-left:None;color: white"><br />YELLOW (#C9C472)<br /><br /></blockquote>
<blockquote STYLE="background-color: #88CE81;border-left:None;color: white"><br />GREEN (#88CE81)<br /><br /></blockquote>
<blockquote STYLE="background-color: #E97768;border-left:None;color: white"><br />RED (#E97768)<br /><br /></blockquote>
<blockquote STYLE="background-color: #75B5E7;border-left:None;color: white"><br />BLUE (#75B5E7)<br /><br /></blockquote>
<blockquote STYLE="background-color: #59CCB4;border-left:None;color: white"><br />LIGHTGREEN (#59CCB4)<br /><br /></blockquote>
<blockquote STYLE="background-color: #75D8E7;border-left:None;color: white"><br />SKY (#75D8E7)<br /><br /></blockquote>
<blockquote STYLE="background-color: #EEEA86;border-left:None;color: white"><br />EGG (#EEEA86)<br /><br /></blockquote>
<blockquote STYLE="background-color: #E89E63;border-left:None;color: white"><br />ORANGE (#E89E63)<br /><br /></blockquote>
<blockquote STYLE="background-color: #DBBDEB;border-left:None;color: white"><br />VIOLET (#DBBDEB)<br /><br /></blockquote>
<blockquote STYLE="background-color: #39B294;border-left:None;color: white"><br />TEAL (#39B294)<br /><br /></blockquote>
<blockquote STYLE="background-color: #73BA5A;border-left:None;color: white"><br />GRASS (#73BA5A)<br /><br /></blockquote>
<blockquote STYLE="background-color: #E65E6D;border-left:None;color: white"><br />SCARLET (#E65E6D)<br /><br /></blockquote>
-->


### Charts

|  Color  |  Description  | HEX value|
|---------|---------------|----------|
| ![Secondary (#505C6D)](media/style/505C6D.png "Secondary (#505C6D)")|-|#505C6D|
| ![Secondary (#008089)](media/style/008089.png "Secondary (#505C6D)")|-|#008089|
|![Primary (#00B7C3)](media/style/00B7C3.png "Primary (#00B7C3)")|Primary color|#00B7C3|
|![YELLOW (#C9C472)](media/style/C9C472.png "YELLOW (#C9C472)")|Yellow|#C9C472|
|![RED (#E97768)](media/style/E97768.png "RED (#E97768)")|Red|#E97768|
|![BLUE (#75B5E7)](media/style/75B5E7.png "BLUE (#75B5E7)")|Blue|#75B5E7|
|![LIGHTGREEN (#59CCB4)](media/style/59CCB4.png "LIGHTGREEN (#59CCB4)")|Light green|#59CCB4|
|![SKY (#75D8E7)](media/style/75D8E7.png "SKY (#75D8E7)")|Sky|75D8E7|
|![EGG (#EEEA86)](media/style/EEEA86.png "EGG (#EEEA86)")|Egg|EEEA86|
|![VIOLET (#DBBDEB)](media/style/DBBDEB.png "VIOLET (#DBBDEB)")|Violet|#DBBDEB|
|![TEAL (#39B294)](media/style/39B294.png "TEAL (#39B294)")|Teal|#39B294|
|![GRASS (#73BA5A)](media/style/73BA5A.png "GRASS (#73BA5A)")|Grass|#73BA5A|

<!--

<blockquote STYLE="background-color: #505C6D;border-left:None;color: white"><br />#505C6D<br /><br /></blockquote>
<blockquote STYLE="background-color: #008089;border-left:None;color: white"><br />#008089<br /><br /></blockquote>
<blockquote STYLE="background-color: #00B7C3;border-left:None;color: white"><br />#00B7C3<br /><br /></blockquote>
<blockquote STYLE="background-color: #C9C472;border-left:None;color: white"><br />#C9C472<br /><br /></blockquote>
<blockquote STYLE="background-color: #E97768;border-left:None;color: white"><br />#E97768<br /><br /></blockquote>
<blockquote STYLE="background-color: #75B5E7;border-left:None;color: white"><br />#75B5E7<br /><br /></blockquote>
<blockquote STYLE="background-color: #59CCB4;border-left:None;color: white"><br />#59CCB4<br /><br /></blockquote>
<blockquote STYLE="background-color: #75D8E7;border-left:None;color: white"><br />#75D8E7<br /><br /></blockquote>
<blockquote STYLE="background-color: #EEEA86;border-left:None;color: white"><br />#EEEA86<br /><br /></blockquote>
<blockquote STYLE="background-color: #DBBDEB;border-left:None;color: white"><br />#DBBDEB<br /><br /></blockquote>
<blockquote STYLE="background-color: #39B294;border-left:None;color: white"><br />#39B294<br /><br /></blockquote>
<blockquote STYLE="background-color: #73BE5A;border-left:None;color: white"><br />#73BE5A<br /><br /></blockquote>

-->
### Miscellaneous colors
|  Color  |  Description  |  HEX value  |  RGB value |
|---------|---------------|-------------|------------|
|![White (#FFFFFF)](media/style/FFFFFF.png "White (#FFFFFF)")|White|#FFFFFF|255, 255, 255|
|![Black (#000000)](media/style/000000.png "Black (#FFFFFF)")|Black|#000000|0, 0, 0|
## Typography

### Fonts


<blockquote STYLE="font-family: Segoe UI;border-left:None"><br />Segoe UI<br /><br /></blockquote>
<blockquote STYLE="font-family: Segoe UI Light;border-left:None"><br />Segoe UI Light<br /><br /></blockquote>
<blockquote STYLE="font-family: Segoe UI;border-left:None"><br /><b>Segoe UI Bold</b><br /><br /></blockquote>
<blockquote STYLE="font-family: Segoe UI Semibold;border-left:None"><br />Segoe UI Semibold<br /><br /></blockquote>


## See Also  
 [Development](Development.md)