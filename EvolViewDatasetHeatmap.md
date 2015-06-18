

## heatmap overview ##

**_NOTE_**

  1. _please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._
  1. **_please consult the tree 'heatmaps' in the DEMOS project to see the Heatmap in action_**
  1. when exported to pdf using Firefox, the color gradient in the legend is known to be wrong; therefore Google Chrome is strongly recommended.

First, let's see some examples:

Let's start with a simple tree:
```
(A:0.1,(B:0.2,(C:0.3,D:0.4)100:0.05)100:0.1)90:0.43;
```

... and an example dataset:
<table border='0'>
<tr>
<td>
<pre>
#heatmap<br>
!legendTitle	Example of heatmap<br>
!showLegends	1<br>
#!defaultStrokeColor	pink<br>
#!defaultStrokeWidth	2<br>
!colorgradient	blue, yellow,red<br>
!colorgradientMarkLabel	0,5,10,15,20,25<br>
# -- heatmap column labels --<br>
!showHeatMapColumnLabel	1<br>
!heatmapColumnLabels	e1,e2,e3,control<br>
# -- heatmap --<br>
!heatmap	margin=2,colwidth=30,roundedcorner=2<br>
# -- show data value<br>
!showdataValue	show=1,fontsize=12,fontitalic=0,textalign=start<br>
A	-2,3,5,0<br>
B	7,9,10,23<br>
C	13,15,19,8<br>
D	20,22,25,4<br>
</pre>
</td>
</tr>
</table>

here is how the plot looks like (with annotations):

![https://www.evernote.com/shard/s130/sh/ebc6be7e-5c38-4620-99d6-d47e80418d70/664b99955ba76fa9089b61916cb32869/res/b2f72be2-82fc-4aef-8188-756cf611b8b1/skitch.png](https://www.evernote.com/shard/s130/sh/ebc6be7e-5c38-4620-99d6-d47e80418d70/664b99955ba76fa9089b61916cb32869/res/b2f72be2-82fc-4aef-8188-756cf611b8b1/skitch.png)

## supported 'modifiers' ##

The following 'modifiers' (Key-Value pairs) are supported for bar charts:

| **Key** (case insensitive) | **Value** | **Description** |
|:---------------------------|:----------|:----------------|
| _**universal modifiers**_  |           |                 |
| `!`Title or `!`Legend      | text      | title of the legend; default = name of the dataset |
| `!`ShowLegends             | 0 or 1    | 0 : hide legends; 1 : show legends |
| `!`opacity                 | float number between 0 to 1 | opacity of the dataset |
| _**modifiers shared with Bar Charts and Dot plots**_  |           | modifiers that apply to both Bar Charts, Dot Plots and Heatmap |
| `!`gridlabel or `!`axis or **`!`showHeatMapColumnLabel** | none, or any integer; 0 : hide column labels; >= 1: show column labels; **note**: using **`!`showHeatMapColumnLabel** here is recommended  | show heatmap column labels (note: does not work in circular modes) |
| `!`defaultStrokeWidth      | any value >= 0 | stroke width that applies to both legends and the chart |
| `!`defaultStrokeColor      | any valid color name such as red and yellow and html hex color such as #FF00FF | stroke color that applies to both legends and the chart; see [here for more about stroke colors](EvolViewAboutStroke.md); also see the section [bellow](EvolViewDatasetDotplots#strokes.md) |
| _**heatmap specific**_     |           |                 |
| `!`colorgradient or `!`colorspectrum | two or more valid colors separated by ','; a color gradient will be generated using the specified colors (see more examples bellow); this modifier is **mandatory** | valid colors include html color names (such as red, yellow, lightblue; see [here](http://www.w3.org/TR/css3-color/#svg-color) for a complete list of supported html color names)  as well as html hex colors such as #FF00FF  |
| `!`colorgradientMarkLabel or `!`colorgradientMarkLabels | one or more valid numbers separated by ',' such as -3,2,5,7,9,10.5; see bellow for more examples  | numbers to be plotted in the legend next to the color gradient |
| `!`heatmapColumnLabel or `!`heatmapColumnLabels | one or more text strings separated by ',', such as trait 1,trait 2,control; see bellow for more examples  | texts to be plotted on the top of the heatmap, each text string corresponds to a column of the heatmap; **NOTE** not implemented yet in circular mode |
| `!`colorGradientPixelHeight or `!`colorGradientHeight | any integer > 1 | pixel height of the color gradient in the legend, default = 100 |
| `!`colorGradientPixelWidth or `!`colorGradientWidth | any integer > 1 | pixel width of the color gradient in the legend, default = 15 |
| `!`heatmap                 | see section [the !heatmap modifier](EvolViewDatasetHeatmap#the_!heatmap_modifier.md) | optional        |
| _**show data values**_     |  see section [show data value](EvolViewDatasetHeatmap#show_data_value.md) for more details  |                 |
| _**unsupported modifiers**_ |  modifiers that are not supported in Heatmap |                 |
| `!`Groups or `!`LegendText |           |                 |
| `!`LegendStyle or `!`Style  |           |                 |
| `!`LegendColors or `!`Colors |           |                 |
| `!`grid                    |           |                 |
| `!`plotwidth               |           |                 |

## notes on preparing your datasets!! ##
  1. **please always use TAB to separate the modifiers and their values.**
  1. **if a modifier is used (accidentally) multiple tiles, only the last one will be used.**
  1. **the "data" part of this dataset can only contain two columns of tab-delimited texts; the third column, if presents, will be ignored**
  1. **please also always use TAB to separate the columns in the data section.**

## strokes ##

Stroke color and width is supported in heat plot; the corresponding modifiers are !defaultStrokeColor and !defaultStrokeWidth.

!defaultStrokeWidth is optional with the default value of 1.

Here is an example:

![https://www.evernote.com/shard/s130/sh/87704e67-adeb-42c0-896d-ac1bcd469cf4/197236089616b656414877675c18f407/res/cbba43c1-4efb-4c85-97e2-2cea94152b3f/skitch.png](https://www.evernote.com/shard/s130/sh/87704e67-adeb-42c0-896d-ac1bcd469cf4/197236089616b656414877675c18f407/res/cbba43c1-4efb-4c85-97e2-2cea94152b3f/skitch.png)

The corresponding dataset is here:

<table border='0'>
<tr>
<td>
<pre>
#heatmap<br>
!title	Example of heatmap<br>
!showLegends	1<br>
!defaultStrokeColor	gold<br>
!defaultStrokeWidth	2<br>
!colorgradient	green, yellow,red<br>
!colorgradientMarkLabel	0,5,10,15,20,25<br>
# -- heatmap column labels --<br>
!showHeatMapColumnLabel	1<br>
!heatmapColumnLabels	e1,e2,e3,control<br>
# -- heatmap --<br>
!heatmap	margin=2,colwidth=30,roundedcorner=2<br>
# -- show data value<br>
!showdataValue	show=1,fontsize=12,fontitalic=0,textalign=start<br>
A	-2,3,5,0<br>
B	7,9,10,23<br>
C	13,15,19,8<br>
D	20,22,25,4<br>
</pre>
</td>
</tr>
</table>

Please see [here](EvolViewAboutStroke.md) for more about stroke color and width.

## the !heatmap modifier ##

The 'value' of the 'key' _**!heatmap**_ can be any combination of the following, separated by a ",":

margin=2,colwidth=30,roundedcorner=2

Please note the !heatmap modifier is optional; if omitted, default values will be used.

|  | **alternative value** | **description** |
|:-|:----------------------|:----------------|
| colwidth=30 | any integer > 0       | set pixel width per column ; optional; default = 20 |
| margin=2 | any integer >= 0      | set pixel space between columns; optional; default = 0 |
| roundedcorner=1 | any integer >= 0      | set rounded corner in pixels for rectangular; valid when shape=rect; optional, default = 0 |

Here are examples showing how these attributes work:


<table border='1'>
<tr><th>Dataset</th><th>Plot</th></tr>


<tr> <td> <b> no <code>!</code>heatmap, everything is by default </b> </td> </tr>

<tr>
<td>
<pre>
#heatmap<br>
!title	Example of heatmap<br>
!showLegends	1<br>
#!defaultStrokeColor	gold<br>
#!defaultStrokeWidth	2<br>
!colorgradient	green, yellow,red<br>
!colorgradientMarkLabel	0,5,10,15,20,25<br>
# -- heatmap column labels --<br>
!showHeatMapColumnLabel	1<br>
!heatmapColumnLabels	e1,e2,e3,control<br>
# -- heatmap --<br>
#!heatmap	margin=2,colwidth=30,roundedcorner=2<br>
# -- show data value<br>
!showdataValue	show=1,fontsize=12,fontitalic=0,textalign=start<br>
A	0,3,5,6<br>
B	7,9,10,12<br>
C	13,15,16,19<br>
D	20,22,23,25<br>
</pre>
</td>


<td>
<img src='https://www.evernote.com/shard/s130/sh/32e35727-6a61-4083-b3bc-190f79a60b38/34c67dd80c6f4f2b67fd75bfc80d19c8/res/b90a0f83-d4ae-4123-89b8-e0df8d06850d/skitch.png' />
</td>

</tr>



<tr> <td> <b> margin=2 </b> </td> </tr>

<tr>
<td>
<pre>
!heatmap	margin=2,colwidth=20<br>
</pre>
</td>


<td>
<img src='https://www.evernote.com/shard/s130/sh/ddd4983c-0d1b-486f-8748-7bd20f0d133c/c4d990bfb9be0c48e7bd992aed86799a/res/1805b277-3d8c-4b85-9680-fb8e1cae0604/skitch.png' />
</td>

</tr>


<tr> <td> <b> roundedcorner=5 </b> </td> </tr>

<tr>
<td>
<pre>
!heatmap	margin=2,colwidth=30,roundedcorner=5<br>
</pre>
</td>


<td>
<img src='https://www.evernote.com/shard/s130/sh/97ba0064-3051-4e19-a904-32725fd7bd2e/bec3e8d6e69041b64177780abe0f08cc/res/9b7e48cb-e0c3-4ccd-9ee8-4e8360d6b812/skitch.png' />
</td>

</tr>





</table>

## show data value ##

The 'value' of the 'key' _**!showdataValue**_ can be any combination of the following, separated by a ",":

|  | **alternative value** | **description** |
|:-|:----------------------|:----------------|
| show = 1 | 0                     | show or hide data values; optional; the data values will be shown if omitted |
| fontsize=12 | any integer           | set font size; optional; default = 10 |
| fontcolor=red | any value color name  | set text color; optional; default = 'black' or 'white' depending on the background color |
| fontitalic=1 | 0                     | set font italic; optional; default = 0 |


**NOTE:** when 'fontcolor' is omitted, a 'black' or 'white' color will be chosen automatically depending the background color of each value in order to increase readability.

## color gradient ##

Creating color gradient is very easy in EvolView by using the !colorgradient or !colorspectrum modifier. Here are a few examples:

<table border='1'>
<tr><th>Dataset</th><th>Plot</th></tr>


<tr>
<td>
<pre>
#heatmap<br>
!title	Example of heatmap<br>
!showLegends	1<br>
#!defaultStrokeColor	gold<br>
#!defaultStrokeWidth	2<br>
!colorgradient	green, yellow,red<br>
!colorgradientMarkLabel	0,5,10,15,20,25<br>
# -- heatmap column labels --<br>
!showHeatMapColumnLabel	1<br>
!heatmapColumnLabels	e1,e2,e3,control<br>
# -- heatmap --<br>
!heatmap	margin=2,colwidth=30,roundedcorner=2<br>
# -- show data value<br>
!showdataValue	show=1,fontsize=12,fontitalic=0,textalign=start<br>
A	0,3,5,6<br>
B	7,9,10,12<br>
C	13,15,16,19<br>
D	20,22,23,25<br>
</pre>
</td>

<td>
<img src='https://www.evernote.com/shard/s130/sh/107661f6-4182-4253-924c-36b6ead56061/50bb914607878de5b496b23a0d33a001/res/9cf50882-be0f-4ad5-831a-6c42462e2df6/skitch.png' />
</td>

</tr>


<tr>
<td>
<pre>
## -- red to white to blue --<br>
!colorgradient	red,white,blue<br>
</pre>
</td>

<td>
<img src='https://www.evernote.com/shard/s130/sh/44d70834-aeb4-4fb0-86cc-258eb06a6f0a/c9c06609fa5ab4562c3be3bacd8fbd1c/res/5b2444ff-a1c1-4845-a3d6-d4dca88bd0e3/skitch.png' />
</td>
</tr>



<tr>
<td>
<pre>
## -- grays; only two colors here --<br>
!colorgradient	black,white<br>
</pre>
</td>

<td>
<img src='https://www.evernote.com/shard/s130/sh/92c73c7a-edc6-494d-905d-a0aafe5b6a98/80437e42b6ee42c672162cf7ce281cd6/res/ddfd893f-6b10-4c11-9867-51961ac87e07/skitch.png' />
</td>
</tr>


<tr>
<td>
<pre>
## -- use five colors this time --<br>
!colorgradient	blue,red,yellow,white,green<br>
</pre>
</td>

<td>
<img src='https://www.evernote.com/shard/s130/sh/f9f5d53f-5624-4886-9975-9db5ec1f0e3e/da3b7385b8910e83a2297004f790e2a2/res/79437190-9b9d-463f-9d50-d9336d878b36/skitch.png' />
</td>
</tr>

</table>

## tick labels of the color gradient of the legend ##

EvolView calculates automatically where the ticks and tick labels to plot on the color gradient of the legend, based on the min and max of user data. However, the results are not always up to users' standard. Users can use modifier !colorgradientMarkLabel / !colorgradientMarkLabels to customize the tick labels.

The value of the modifier is one or more valid numbers, separated by ','. Here are some examples:

<table border='1'>
<tr><th>Dataset</th><th>Plot</th></tr>


<tr> <td> <b> color gradient tick labels are automatically positioned </b> </td> </tr>

<tr>
<td>
<pre>
#heatmap<br>
!title	Example of heatmap<br>
!showLegends	1<br>
!colorgradient	blue,red,yellow,white,green<br>
!showHeatMapColumnLabel	1<br>
!heatmapColumnLabels	e1,e2,e3,control<br>
!heatmap	margin=1,colwidth=30,roundedcorner=0<br>
!showdataValue	show=1,fontsize=12,fontitalic=0<br>
A	-1,3,5,6<br>
B	7,9,10,12<br>
C	13,15,16,19<br>
D	20,22,23,25<br>
</pre>
</td>


<td>
<img src='https://www.evernote.com/shard/s130/sh/e10d66b6-1306-49f5-834a-0652bc076384/e2b3583cc1de85dcf6df17749db78343/res/0988b3be-59f5-4b6b-9661-f017dd74cafb/skitch.png' />
</td>

</tr>



<tr> <td> <b> customized tick labels using <code>!</code>colorgradientMarkLabel  </b> </td> </tr>

<tr>
<td>
<pre>
!colorgradientMarkLabel	0,5,10,15,20,25<br>
</pre>
</td>


<td>
<img src='https://www.evernote.com/shard/s130/sh/4f531802-77bf-46c9-ba88-b7ad22ba4965/271dc8512177a4203d78e20f73019558/res/e35847a1-d5b0-4f81-837e-780b1fca73da/skitch.png' />
</td>

</tr>
</table>