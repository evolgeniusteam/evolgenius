

**_NOTE_**

_please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._

## color strips / shapes overview ##

Similar to bar charts, color strips and color shapes are added next to the leaf labels. Therefore multiple datasets can be uploaded and displayed.

Here is an example:

![https://lh3.googleusercontent.com/-mL1c8cXYBkk/UahT0jcu1xI/AAAAAAAAAMA/jlQrCJOuCyE/w506-h306-o/ev.strips.010.png](https://lh3.googleusercontent.com/-mL1c8cXYBkk/UahT0jcu1xI/AAAAAAAAAMA/jlQrCJOuCyE/w506-h306-o/ev.strips.010.png)

the differences between 'rect' and 'strip' are:
  * strip by default will take all available space of a leaf label, while rect will only take 80%
  * strip looks like the following in circular mode, while rect remains the same.

![https://lh4.googleusercontent.com/-sO80RpGbba0/UadRY1RpegI/AAAAAAAAALc/RJ5iNmhCLr0/w360-h297-no/ev.strips.002.png](https://lh4.googleusercontent.com/-sO80RpGbba0/UadRY1RpegI/AAAAAAAAALc/RJ5iNmhCLr0/w360-h297-no/ev.strips.002.png)

## supported modifiers ##

Supported Key-Value pairs for color charts:
| **Key** (case insensitive) | **Value** | **Description** |
|:---------------------------|:----------|:----------------|
| _**universal modifiers**_  |           |                 |
| `!`Groups or `!`LegendText |comma separated text| Legend texts; for example 'group\_a,group\_b,group\_c'|
| `!`LegendStyle or `!`Style  | rect or circle or star | shapes to be plotted before the legend texts; default = rect |
| `!`LegendColors or `!`Colors |comma separated color codes or names| colors to be applied to the shapes specified by LegendStyle; for example 'red,green,yellow' ; note the number of colors should match the number of legend fields|
| `!`Title or `!`Legend      | text      | title of the legend; default = name of the dataset |
| `!`ShowLegends             | 0 or 1    | 0 : hide legends; 1 : show legends |
| `!`opacity                 | float number between 0 to 1 | opacity of the dataset |
| _**none-universal modifiers**_  |           |                 |
| `!`PlotWidth               | integer > 0 | pixel width of the dataset on canvas |
| `!`itemHeightPX or `!`barHeightPX | integer > 0 | pixel height of each shape except 'strips'; see examples bellow |
| `!`itemHeightPCT or `!`barHeightPCT | float number between 1 to 100 | percentage of available height taken by each shape except 'strips'; see examples bellow |
| _**unique modifiers**_     |           | modifiers for this annotation dataset only |
|  `!`type or  `!`types or  `!`shape or  `!`shapes | any one or combination of rect,star,circle,strip,check | see examples bellow |
| `!`stripHeightPX           | integer > 0 | pixel height for each strip; see examples bellow |
| `!`stripHeightPCT          | float number between 1 to 100 | percentage of available height taken each strip, see examples bellow |
| `!`checkLineWidth or `!`checklwd | integer > 0 | line width of the 'check' symbol, see examples bellow |


## notes on preparing your datasets!! ##
  1. **please always use TAB to separate the modifiers and their values.**
  1. **modifier !type controls the number of shapes to be shown next to leaf labels**
  1. **the "data" part of this dataset can only contain two columns of tab-delimited texts; the third column, if presents, will be ignored**
    * the first column contains the name of a single leaf node
    * the second column contains comma (,) delimited colors; if the number of colors is less than the number of shapes, the colors will be recycled
  1. **please also always use TAB to separate the columns in the data section.**


## examples ##
Here is the tree:
```
(chicken,((mouse,rat),(chimp,human)));
```
<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<blockquote><pre>
##color strips<br>
!type		strip,rect,circle,star<br>
!showlegends	0<br>
<br>
## let the data begin<br>
mouse	pink,red,green,blue<br>
chicken	yellow,purple,darkred,lightgreen<br>
rat	lightblue<br>
chimp	grey,darkgreen,grey,pink<br>
human	orange,red,yellow,lightblue<br>
</pre>
</td><td>
<img src='https://www.evernote.com/shard/s130/sh/adc6b356-e863-4f84-a3c0-9774af069ea1/be18c5f3c983b80d6009ca8edcec3c5a/res/bacc3ab2-7311-484e-823c-524596bc1df4/skitch.png' />
</td></tr></table></blockquote>

## plot width, widths and heights of individual shapes ##

Here is how widths and heights of individual shapes are calculated:
  * if a dataset contains multiple shapes, then the plot width will be divided equally among each shape
  * each shape will take 80% of available width
  * each shape will take 80% of available height, except strip, while will take 100%
  * all shapes will be centered at the available space both vertically and horizontally
  * for all shapes except strips, when the widths and heights are of different sizes, always the smaller ones will be chosen as their widths and heights
  * by default, strips will take all of the available heights; however, user can change that using two modifiers !stripHeightPX and !stripHeightPCT. When both modifiers are used in the same dataset (by mistake), only !stripHeightPCT will be used.

Here are some examples:
<table border='1'>
<tr>
<th>Modifiers tested</th>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td></td>
<td>
<blockquote><pre>
##color strips<br>
!type	strip,check,rect,star,circle<br>
A	red,green,blue<br>
B	purple,darkred,lightgreen<br>
C	lightblue<br>
D	darkgreen,grey,pink<br>
</pre>
</td>
<td><img src='https://lh3.googleusercontent.com/-FFC9cNzLZhM/UahZNXB3yGI/AAAAAAAAAM0/da6BbQlG9Us/w245-h176-no/Screen+Shot+2013-05-31+at+9.52.05+AM.png' /></td>
</tr></blockquote>

<tr>
<td>!plotWidth</td>
<td>
<blockquote><pre>
##color strips<br>
!type	strip,check,rect,star,circle<br>
## plotwidth by default is 100; set to 200 in this example<br>
!plotWidth	200<br>
A	red,green,blue<br>
B	purple,darkred,lightgreen<br>
C	lightblue<br>
D	darkgreen,grey,pink<br>
</pre>
</td>
<td><img src='https://lh6.googleusercontent.com/-193Ote_J2m0/UahZNaAA4JI/AAAAAAAAAM8/f4P31Hbl6R8/w326-h163-no/Screen+Shot+2013-05-31+at+9.54.08+AM.png' /></td>
</tr></blockquote>

<tr>
<td>!itemHeightPCT</td>
<td>
<blockquote><pre>
##color strips<br>
!type	strip,check,rect,star,circle<br>
!plotWidth	200<br>
## -- shapes except strip will take 80% of available space; make it 100% in this example --<br>
!itemHeightPCT	100<br>
A	red,green,blue<br>
B	purple,darkred,lightgreen<br>
C	lightblue<br>
D	darkgreen,grey,pink<br>
</pre>
</td>
<td><img src='https://lh3.googleusercontent.com/-TH1EUbKvovw/UahZOCklmAI/AAAAAAAAANM/feXpVs85dbA/w326-h164-no/Screen+Shot+2013-05-31+at+9.56.33+AM.png' /></td>
</tr></blockquote>

<tr>
<td>!stripHeightPCT</td>
<td>
<blockquote><pre>
##color strips<br>
!type	strip,check,rect,star,circle<br>
## -- by default, strip will always take 100% available height; make it 80 in this example --<br>
!stripHeightPCT	80<br>
A	red,green,blue<br>
B	purple,darkred,lightgreen<br>
C	lightblue<br>
D	darkgreen,grey,pink<br>
</pre>
</td>
<td><img src='https://lh5.googleusercontent.com/-xMu_SH3uOd4/UahZONknaPI/AAAAAAAAANQ/LIBguooSbpE/w242-h147-no/Screen+Shot+2013-05-31+at+9.58.27+AM.png' /></td>
</tr></blockquote>

<tr>
<td>!stripHeightPCT</td>
<td>
<pre>
## the same as previous one, but the tree is plotted in circular mode<br>
</pre>
</td>
<td><img src='https://lh6.googleusercontent.com/-v_wTYv69MMY/UahZOarRHRI/AAAAAAAAANU/9ETANyh1RMk/w314-h349-no/Screen+Shot+2013-05-31+at+9.59.40+AM.png' /></td>
</tr>

<tr>
<td>!checkLineWidth</td>
<td>
<pre>
##color strips<br>
!type	strip,check,rect,star,circle<br>
## -- by default, check has a line width of 2 pixel; make it 5 --<br>
!checkLineWidth	5<br>
A	red,green,blue<br>
B	purple,darkred,lightgreen<br>
C	lightblue<br>
D	darkgreen,grey,pink<br>
</pre>
</td>
<td><img src='https://lh3.googleusercontent.com/-GJhqEbcIo1o/UahZNSCmtbI/AAAAAAAAANA/pNe1H2pxRJ0/w232-h144-no/Screen+Shot+2013-05-31+at+10.01.32+AM.png' /></td>
</tr>
</table>