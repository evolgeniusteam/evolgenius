

## dot plots overview ##

**_NOTE_**

_please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._

**_please consult the tree 'dotplots' in the DEMOS project to see the dotplots in action_**

Dot plot is a variant of [Bar chart](EvolViewDatasetBars.md), therefore a dataset for Bar charts can be used directly.

First, let's see some examples:

Let's start with a simple tree:
```
(A:0.1,(B:0.2,(C:0.3,D:0.4)100:0.05)100:0.1)90:0.43;
```

... and an example dataset:
<table border='0'>
<tr>
<td>
<blockquote><pre>
##dot plots<br>
!groups	dot 1,dot 2,dot 3<br>
!colors	#028482,#7ABA7A,yellow<br>
!title	Example of dot plot<br>
# -- legends --<br>
!legendstyle	circle<br>
!showLegends	1<br>
## -- if !scalebycol is set to 1, each column of data will be scaled independently<br>
!scalebycol	0<br>
!byarea	1<br>
# ---- grid and grid label / group label are also supported --<br>
!grid	1<br>
!gridlabel	1<br>
# stroke and stroke color also work here<br>
!defaultStrokeColor	pink<br>
#!defaultStrokeWidth	2<br>
# here shape can be 'rect' or 'circle'; roundedcorner only applies to 'rect' shapes ...<br>
!dotplots	shape=circle,margin=2,colwidth=30,roundedcorner=3<br>
## -- show data value works at here as well --<br>
!showdataValue	show=1,fontsize=12,fontitalic=0,fontcolor=black<br>
A	8,13,5<br>
B	10,20,20<br>
C	8,9,7<br>
D	20,20,20<br>
</pre>
</td>
</tr>
</table></blockquote>

here is how the plot looks like:

![https://www.evernote.com/shard/s130/sh/2243ad16-1f95-45ef-b35e-7cbf7e7e466f/bff76fb9b9eff51464723c49a8223b9e/res/af4566e9-4925-4037-ba7e-2bd9ec128f98/skitch.png](https://www.evernote.com/shard/s130/sh/2243ad16-1f95-45ef-b35e-7cbf7e7e466f/bff76fb9b9eff51464723c49a8223b9e/res/af4566e9-4925-4037-ba7e-2bd9ec128f98/skitch.png)

By default, data are represented by dots / filled circles; however they could be alternatively represented by rectangular:

![https://www.evernote.com/shard/s130/sh/275854cf-6f98-41f1-8e87-b323bce98fc6/d252b32889ab7627a9286c7f07015d2a/res/790adf2a-41e3-40c2-8c3a-f0884dd0f598/skitch.png](https://www.evernote.com/shard/s130/sh/275854cf-6f98-41f1-8e87-b323bce98fc6/d252b32889ab7627a9286c7f07015d2a/res/790adf2a-41e3-40c2-8c3a-f0884dd0f598/skitch.png)

Here is the dataset:

<table border='0'>
<tr>
<td>
<blockquote><pre>
##dot plots<br>
!groups	dot 1,dot 2,dot 3<br>
!colors	#028482,#7ABA7A,yellow<br>
!title	Example of dot plot<br>
!legendstyle	rect<br>
!showLegends	1<br>
!byarea	1<br>
!grid	1<br>
!gridlabel	1<br>
!defaultStrokeColor	pink<br>
#!defaultStrokeWidth	2<br>
!dotplots	shape=rect,margin=2,colwidth=30,roundedcorner=3<br>
!showdataValue	show=1,fontsize=12,fontitalic=0,textalign=start,fontcolor=black<br>
A	8,13,5<br>
B	10,20,20<br>
C	8,9,7<br>
D	20,20,20A	8,13,5<br>
B	10,20,20<br>
C	8,9,7<br>
D	20,20,20<br>
</pre>
</td>
</tr>
</table></blockquote>

## supported 'modifiers' ##

The following 'modifiers' (Key-Value pairs) are supported for bar charts:

| **Key** (case insensitive) | **Value** | **Description** |
|:---------------------------|:----------|:----------------|
| _**universal modifiers**_  |           |                 |
| `!`Groups or `!`LegendText |comma separated text| Legend texts; for example 'group\_a,group\_b,group\_c'|
| `!`LegendStyle or `!`Style  | rect or circle or star | shapes to be plotted before the legend texts; default = rect |
| `!`LegendColors or `!`Colors |comma separated color codes or names| colors to be applied to the shapes specified by LegendStyle; for example 'red,green,yellow' ; note the number of colors should match the number of legend fields|
| `!`Title or `!`Legend      | text      | title of the legend; default = name of the dataset |
| `!`ShowLegends             | 0 or 1    | 0 : hide legends; 1 : show legends |
| `!`opacity                 | float number between 0 to 1 | opacity of the dataset |
| _**modifiers shared with Bar Charts**_  |           | modifiers that apply to both Bar Charts and Dot Plots |
| `!`grid                    | none      | show a background grid |
| `!`gridlabel or `!`axis    | none      | show grid labels (note: does not work in circular modes |
| `!`defaultStrokeWidth      | any value >= 0 | stroke width that applies to both legends and the chart |
| `!`defaultStrokeColor      | any valid color name such as red and yellow and html hex color such as #FF00FF | stroke color that applies to both legends and the chart; see [here for more about stroke colors](EvolViewAboutStroke.md); also see the section [bellow](EvolViewDatasetDotplots#strokes.md) |
| _**dot plots specific**_   |           |                 |
| `!`scalebycol              | none      | scale the data by column, i.e. the max value in a column will take the maximum plot width of a column; default is to scale by the maximum of all data  |
| `!`dotplots                | see section [the !dotplots modifier](EvolViewDatasetDotplots#the_!dotplots_modifier.md) |                 |
| _**show data values**_     |  see section [show data value](EvolViewDatasetDotplots#show_data_value.md) for more details  |                 |

## notes on preparing your datasets!! ##
  1. **please always use TAB to separate the modifiers and their values.**
  1. **if a modifier is used (accidentally) multiple tiles, only the last one will be used.**
  1. **the "data" part of this dataset can only contain two columns of tab-delimited texts; the third column, if presents, will be ignored**
  1. **please also always use TAB to separate the columns in the data section.**

## strokes ##

User can choose different stroke colors for different columns using the modifier **!colors**; for example, by simply changing the value of **!colors** to :

```
#028482:blue,#7ABA7A:gold,#B76EB8:darkgrey
```

we can have a dot plot like the following:

![https://www.evernote.com/shard/s130/sh/d01ab0f3-b213-46bc-87c5-3817a58d9157/9d5926e91e93e02a286517a94c4ed19b/res/29648713-6be9-48f1-9850-74af999c1aa3/skitch.png](https://www.evernote.com/shard/s130/sh/d01ab0f3-b213-46bc-87c5-3817a58d9157/9d5926e91e93e02a286517a94c4ed19b/res/29648713-6be9-48f1-9850-74af999c1aa3/skitch.png)

Here is the complete version of the dataset:

<table border='0'>
<tr>
<td>
<blockquote><pre>
##dot plots<br>
!groups	dot 1,dot 2,dot 3<br>
## -- set stroke color --<br>
!colors	#028482:blue,#7ABA7A:gold,#B76EB8:darkgrey<br>
## -- set stroke width to 2 --<br>
#!defaultStrokeColor	pink<br>
!defaultStrokeWidth	2<br>
!title	Example of dot plot<br>
!legendstyle	circle<br>
!showLegends	1<br>
!byarea	1<br>
!grid	1<br>
!gridlabel	1<br>
!dotplots	shape=circle,margin=2,colwidth=30,roundedcorner=3<br>
!showdataValue	show=1,fontsize=12,fontitalic=0,textalign=start,fontcolor=white<br>
A	8,13,5<br>
B	10,20,20<br>
C	8,9,7<br>
D	20,20,20<br>
</pre>
</td>
</tr>
</table></blockquote>

Please see [here](EvolViewAboutStroke.md) for more about stroke color and width.

## the !dotplots modifier ##

The 'value' of the 'key' _**!dotplots**_ can be any combination of the following, separated by a ",":

shape=circle,margin=2,colwidth=30,roundedcorner=3

|  | **alternative value** | **description** |
|:-|:----------------------|:----------------|
| shape = circle | rect                  | shape of the dot plots; default is circle |
| colwidth=30 | any integer > 0       | set pixel width per column ; optional; default = 20 |
| margin=2 | any integer >= 0      | set pixel space between columns; optional; default = 0 |
| roundedcorner=1 | any integer >= 0      | set rounded corner in pixels for rectangular; valid when shape=rect; optional, default = 0 |

## show data value ##

The 'value' of the 'key' _**!showdataValue**_ can be any combination of the following, separated by a ",":

|  | **alternative value** | **description** |
|:-|:----------------------|:----------------|
| show = 1 | 0                     | show or hide data values; optional; the data values will be shown if omitted |
| fontsize=12 | any integer           | set font size; optional; default = 10 |
| fontcolor=red | any value color name  | set text color; optional; default = 'black' or 'white' depending on the background color |
| fontitalic=1 | 0                     | set font italic; optional; default = 0 |


**NOTE:** when 'fontcolor' is omitted, the default font color will be either 'black' or 'white' depending the background color, for example:

![https://www.evernote.com/shard/s130/sh/a412ebd5-bc74-4c8c-abd2-7278a55e74be/6f0beba8e9886e630587466973888e15/res/7ec877c4-6f3d-4734-8e0a-ec5ae5ad215c/skitch.png](https://www.evernote.com/shard/s130/sh/a412ebd5-bc74-4c8c-abd2-7278a55e74be/6f0beba8e9886e630587466973888e15/res/7ec877c4-6f3d-4734-8e0a-ec5ae5ad215c/skitch.png)

The purpose here is to ensure the readability of the texts on any background colors.

Here is the dataset:

<table border='0'>
<tr>
<td>
<blockquote><pre>
!groups	dot 1,dot 2,dot 3<br>
!colors	#028482,#7ABA7A,yellow<br>
!title	Example of dot plot<br>
!legendstyle	circle<br>
!showLegends	1<br>
!byarea	1<br>
!grid	1<br>
!gridlabel	1<br>
!defaultStrokeColor	pink<br>
!dotplots	shape=circle,margin=2,colwidth=30,roundedcorner=3<br>
!showdataValue	show=1,fontsize=12,fontitalic=0,textalign=start<br>
A	8,13,5<br>
B	10,20,20<br>
C	8,9,7<br>
D	20,20,20<br>
</pre>
</td>
</tr>
</table></blockquote>

In this particular case, if we force the text color to 'white':

<table border='0'>
<tr>
<td>
<blockquote><pre>
!groups	dot 1,dot 2,dot 3<br>
!colors	#028482,#7ABA7A,yellow<br>
!title	Example of dot plot<br>
!legendstyle	circle<br>
!showLegends	1<br>
!byarea	1<br>
!grid	1<br>
!gridlabel	1<br>
!defaultStrokeColor	pink<br>
!dotplots	shape=circle,margin=2,colwidth=30,roundedcorner=3<br>
!showdataValue	show=1,fontsize=12,fontitalic=0,textalign=start,fontcolor=white<br>
A	8,13,5<br>
B	10,20,20<br>
C	8,9,7<br>
D	20,20,20<br>
</pre>
</td>
</tr>
</table></blockquote>

... the texts of the 3rd column where the background color is yellow are unreadable:

![https://www.evernote.com/shard/s130/sh/5e8620f3-0619-40ff-9e14-e88492618f47/6544af9dd5045bf169748a251be24624/res/d5cf14a6-510b-48e7-91e3-de01c586cd31/skitch.png](https://www.evernote.com/shard/s130/sh/5e8620f3-0619-40ff-9e14-e88492618f47/6544af9dd5045bf169748a251be24624/res/d5cf14a6-510b-48e7-91e3-de01c586cd31/skitch.png)