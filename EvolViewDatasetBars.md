

## what's new ##

  * added new functionality **show data value** in bar plots, see section: [Show data value](EvolViewDatasetBars#show_data_value.md). Here is an example plot:

![https://lh6.googleusercontent.com/-w_L-89qu89M/VDLtrlgClNI/AAAAAAAAAXs/2ITFC79Mxhs/w359-h175-no/EvolView__project_-_Documentation__tree_-_for_bars.png](https://lh6.googleusercontent.com/-w_L-89qu89M/VDLtrlgClNI/AAAAAAAAAXs/2ITFC79Mxhs/w359-h175-no/EvolView__project_-_Documentation__tree_-_for_bars.png)


## bar charts overview ##


**_NOTE_**

_please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._


Bar charts will be displayed next to leaf labels. For example:

![https://lh5.googleusercontent.com/-QTqELAbTGlI/Uabpm3TmeqI/AAAAAAAAAEU/qXAD8aHVR2o/w465-h236-no/ev.barcharts.001.png](https://lh5.googleusercontent.com/-QTqELAbTGlI/Uabpm3TmeqI/AAAAAAAAAEU/qXAD8aHVR2o/w465-h236-no/ev.barcharts.001.png)

Multiple bar-chart datasets can be uploaded to a tree and shown next to each other; uploaded datasets can be managed using the control panel:

![https://lh5.googleusercontent.com/-YRRm4Qv9LNY/UabuX7N45yI/AAAAAAAAAFA/cQ-ER4xbUws/w567-h284-no/ev.barcharts.002.png](https://lh5.googleusercontent.com/-YRRm4Qv9LNY/UabuX7N45yI/AAAAAAAAAFA/cQ-ER4xbUws/w567-h284-no/ev.barcharts.002.png)


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
| _**none pie chart modifiers**_  |           | modifiers that apply to all charts except pies |
| `!`PlotWidth               | integer > 0 | pixel width of the dataset on canvas |
| `!`itemHeightPX or `!`barHeightPX | integer > 0 | pixel height of each bar; see examples bellow |
| `!`itemHeightPCT or `!`barHeightPCT | float number between 1 to 100 | percentage of available height taken by each bar; see examples bellow |
| `!`grid                    | none      | show a background grid |
| `!`gridlabel or `!`axis    | none      | show the values corresponding to the grid lines |
| _**bar charts specific**_  |           |                 |
| `!`align or `!`alignIndividualColumn | none      | align individual columns if the bars are stacked |
| `!`Fanplot or `!` Fan      | none      | works only with circular tree; see examples bellow |
| _**new: show data values**_ |  see section [show data value](EvolViewDatasetBars#show_data_value.md) for more details  |                 |

## notes on preparing your datasets!! ##
  1. **please always use TAB to separate the modifiers and their values.**
  1. **some modifiers should not be used in combination, e.g. !itemHeightPX and !itemHeightPCT. However if both are used (accidentally), only !itemHeightPX be used.**
  1. **if a modifier is used (accidentally) multiple tiles, only the last one will be used.**
  1. **the "data" part of this dataset can only contain two columns of tab-delimited texts; the third column, if presents, will be ignored**
  1. **please also always use TAB to separate the columns in the data section.**


## some examples ##

the tree :
```
(A:0.1,(B:0.2,(C:0.3,D:0.4)100:0.05)100:0.1)90:0.43;
```

<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<blockquote><pre>
##barplots<br>
!groups	2009,2010,2011<br>
!colors	lightblue,yellow,green<br>
!showLegends	1<br>
!plotwidth	100<br>
!style	rect<br>
!title	an example of bar plots<br>
A	2,3,1<br>
B	10,20,1<br>
C	8,9,2<br>
D	20,3,4<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/4d3d4285-50f2-46a7-9262-0241232e0da7/06693da8232dc7b49a06b83f88ad9a16/res/54f2b7fb-3cc3-4e9a-9490-cec0a681767c/skitch.png' />
</td></tr>
<tr><td>
<pre>
## turn grid on<br>
!grid<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/0aac8ff7-d1f2-47c1-8a0d-65dd38042467/54729bc99c598a52a72ebec537444607/res/eadcb4b7-26e5-4549-b2cd-89f11a939108/skitch.png' />
</td></tr>
<tr><td>
<pre>
## turn grid on<br>
## align individual columns<br>
!grid<br>
!align<br>
</pre>
</td><td>
<img src='https://www.evernote.com/shard/s130/sh/02ca202c-273a-4ea8-a9f9-6bb27c695edb/9b4ddc6845a59fbcb9c0d442bda9acb5/res/5b3d127b-c0fe-4309-a0f1-2ccfadae5e30/skitch.png' />
</td></tr>
<tr><td>
<pre>
## fan plot of the bars in circular mode<br>
!Fanplot<br>
</pre>
</td><td>
<img src='https://www.evernote.com/shard/s130/sh/7bc87909-f53e-405c-a36b-8e523607db36/b8f92e82314be695bda4964534d4ec83/res/c59ce1f2-b19a-40fc-84c3-4a020ecd9ad4/skitch.png' />
</td></tr>
<tr><td>
<pre>
## grid and grid label<br>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
!grid<br>
!gridlabel<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td><td>
<img src='https://lh3.googleusercontent.com/-BQuJsUwk0hw/Uab1vRYZPII/AAAAAAAAAGQ/5EFFsRaGTNA/w394-h339-no/ev.barcharts.004.png' />
</td></tr>
<tr><td>
<pre>
## fan plot of the bars in circular mode<br>
## and align individual columns<br>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
!fanplot<br>
!align<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td><td>
<img src='https://lh3.googleusercontent.com/-XcbQV79KtWw/Uab0LHLJCgI/AAAAAAAAAFk/tG07W3EVTOc/w394-h336-no/ev.barcharts.003.png' />
</td></tr>
</table></blockquote>

## heights of individual bars ##

By default, the height of an individual bar is 10 pixel, it can be changed using two modifiers:
  * !itemHeightPX
  * !itemHeightPCT

**!itemHeightPX** specifies the absolute pixel height for individual bars; its value ranges from >0 to 40. Here are some examples:

<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<blockquote><pre>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
## -- set height for individual bars --<br>
## -- default value is 10 --<br>
!itemHeightPX	10<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td>
<td>
<img src='https://lh3.googleusercontent.com/-y7rmzaiO4nI/UacOYgftrFI/AAAAAAAAAHI/tOjO8LAYngw/w242-h155-no/ev.barcharts.005.png' />
</td>
</tr></blockquote>

<tr>
<td>
<blockquote><pre>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
## -- now we change the height to 20 --<br>
!itemHeightPX	20<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td>
<td>
<img src='https://lh3.googleusercontent.com/-RUCmnMRaN6g/UacOYiheQ0I/AAAAAAAAAHE/7QgVnpUNsLA/w239-h150-no/ev.barcharts.006.png' />
</td>
</tr></blockquote>

<tr>
<td>
<blockquote><pre>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
## -- if the pixel height is larger than the available space,<br>
## -- which is 30 pixel in this case, as indicated by the pink box under leaf node 'A' --<br>
## -- only available space will be taken by the bars (30 pixel) --<br>
!itemHeightPX	35<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td>
<td>
<img src='https://lh5.googleusercontent.com/-5H9vWXAXoOg/UacQrP-fGmI/AAAAAAAAAH4/-jjmHr4B2_I/w250-h154-no/ev.barcharts.007.png' />
</td>
</tr></blockquote>

</table>

**!itemHeightPCT** specifies the percentage of available space taken by a bar; its value ranges from 1 to 100.

<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<blockquote><pre>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
## -- let's first of all take 60% of the space ... --<br>
!itemHeightPCT	60<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td>
<td>
<img src='https://lh3.googleusercontent.com/-1ErKQPGOaAA/UacSs_2b8jI/AAAAAAAAAIw/D7t63lPO6rQ/w251-h147-no/ev.barcharts.008.png' />
</td>
</tr></blockquote>

<tr>
<td>
<blockquote><pre>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
## -- bar height increases / decreases with increasing / decreasing vertical scale --<br>
## -- still taking 60% of the space ... --<br>
!itemHeightPCT	60<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td>
<td>
<img src='https://lh4.googleusercontent.com/-I0EBFjdpE8g/UacSs-DETlI/AAAAAAAAAIs/GZC5vhgNqN0/w257-h288-no/ev.barcharts.009.png' />
</td>
</tr></blockquote>

<tr>
<td>
<blockquote><pre>
## --<br>
</pre>
</td>
<td>
<img src='https://lh4.googleusercontent.com/-kXKuZKK52E0/UacSs0cEVzI/AAAAAAAAAIo/CHhzZlYpnL8/w239-h77-no/ev.barcharts.010.png' />
</td>
</tr></blockquote>

</table>

## show data value ##

First, let's see an example:

the tree :
```
(A:0.1,(B:0.2,(C:0.3,D:0.4)100:0.05)100:0.1)90:0.43;
```

the dataset (copy & paste) :

<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<blockquote><pre>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
!title	Example of barplots 4<br>
!plotwidth	200<br>
!itemHeightPCT	80<br>
!grid<br>
!axis<br>
!showLegends	0<br>
!showdataValue	show=1,fontsize=12,fontitalic=1,textalign=end<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td>
<td>
<img src='https://lh4.googleusercontent.com/-x_mURCFVgSU/VDLw2BlhwUI/AAAAAAAAAYU/YVAjPASyE4A/w350-h160-no/EvolView__project_-_Documentation__tree_-_for_bars.png' />
</td></tr>
</table></blockquote>

A bit more details on supported features: ![https://lh6.googleusercontent.com/-uYKom7L9iGk/VDLyD3BfZpI/AAAAAAAAAY4/NiZOJnVTvi4/w452-h16-no/Edit_EvolViewDatasetBars_-_evolgenius_-_Genius_ways_to_perform_evolutionary_analyses_-_Google_Project_Hosting.png](https://lh6.googleusercontent.com/-uYKom7L9iGk/VDLyD3BfZpI/AAAAAAAAAY4/NiZOJnVTvi4/w452-h16-no/Edit_EvolViewDatasetBars_-_evolgenius_-_Genius_ways_to_perform_evolutionary_analyses_-_Google_Project_Hosting.png).

The 'value' of the 'key' _**!showdataValue**_ can be any combination of the following, separated by a ",":

|  | **alternative value** | **description** |
|:-|:----------------------|:----------------|
| show = 1 | 0                     | show or hide data values; optional; the data values will be shown if omitted |
| fontsize=12 | any integer           | set font size; optional; default = 10 |
| fontcolor=red | any value color name  | set text color; optional; default = black |
| fontitalic=1 | 0                     | set font italic; optional; default = 0 |
| textalign=middle | start or end          | set text align; optional; default = middle; see the following examples |

More examples using the same tree above:

<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<blockquote><pre>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
!title	Example of barplots 4<br>
!plotwidth	200<br>
!itemHeightPCT	80<br>
!grid<br>
!axis<br>
!showLegends	0<br>
!showdataValue	show=1,fontsize=12,fontitalic=1,textalign=end,fontcolor=white<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td>
<td>
<img src='https://lh6.googleusercontent.com/-w_L-89qu89M/VDLtrlgClNI/AAAAAAAAAXs/2ITFC79Mxhs/w359-h175-no/EvolView__project_-_Documentation__tree_-_for_bars.png' /></td></tr></blockquote>

<tr> <td> <b> ###  text align == end in circular mode ### </b> </td> </tr>

<tr>
<td>
<blockquote><pre>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
!title	Example of barplots 4<br>
!plotwidth	200<br>
!itemHeightPCT	80<br>
!grid<br>
!axis<br>
!showLegends	0<br>
!showdataValue	show=1,fontsize=12,fontitalic=1,textalign=end,fontcolor=white<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td>
<td>
<img src='https://lh3.googleusercontent.com/-h5eFtH3ezNU/VDL2ZTVYUDI/AAAAAAAAAZs/1rqw2TIvGlQ/w546-h429-no/EvolView__project_-_Documentation__tree_-_for_bars.png' /></td></tr></blockquote>

<tr> <td> <b> ###  text align == start in circular mode ### </b> </td> </tr>

<tr>
<td>
<blockquote><pre>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
!title	Example of barplots 4<br>
!plotwidth	200<br>
!itemHeightPCT	80<br>
!grid<br>
!axis<br>
!showLegends	0<br>
!showdataValue	show=1,fontsize=12,fontitalic=1,textalign=start,fontcolor=white<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td>
<td>
<img src='https://lh5.googleusercontent.com/-eJj7i2tmmHk/VDL2vpSR0_I/AAAAAAAAAZ0/0KHtCgp_shg/w542-h429-no/EvolView__project_-_Documentation__tree_-_for_bars.png' /></td></tr></blockquote>


</table>