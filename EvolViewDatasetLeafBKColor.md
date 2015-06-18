

**_NOTE_**

_please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._

## leaf backgroud color overview ##

leafbackground colors will change the colors of leaf background. Similar to branch colors, multiple datasets can be uploaded to a tree, but only one can be shown at a time.

Here is an example:
![https://lh3.googleusercontent.com/-u4LeNzBt5Vc/Uac1TQMO4zI/AAAAAAAAAKE/oLUKiu4D36Q/w782-h659-no/ev.bkcolor.001.png](https://lh3.googleusercontent.com/-u4LeNzBt5Vc/Uac1TQMO4zI/AAAAAAAAAKE/oLUKiu4D36Q/w782-h659-no/ev.bkcolor.001.png)

## supported modifiers ##

Supported Key-Value pairs for pie charts:
| **Key** (case insensitive) | **Value** | **Description** |
|:---------------------------|:----------|:----------------|
| _**universal modifiers**_  |           |                 |
| `!`Groups or `!`LegendText |comma separated text| Legend texts; for example 'group\_a,group\_b,group\_c'|
| `!`LegendStyle or `!`Style  | rect or circle or star | shapes to be plotted before the legend texts; default = rect |
| `!`LegendColors or `!`Colors |comma separated color codes or names| colors to be applied to the shapes specified by LegendStyle; for example 'red,green,yellow' ; note the number of colors should match the number of legend fields|
| `!`Title or `!`Legend      | text      | title of the legend; default = name of the dataset |
| `!`ShowLegends             | 0 or 1    | 0 : hide legends; 1 : show legends |
| `!`opacity                 | float number between 0 to 1 | opacity of the dataset |


## data and examples ##
Data are usually tab-delimited three-column texts, with the third column optional.

### first column: the location ###
the first column dictates where the data to be plotted. It usually contains the name of a leaf node, or two leaf names separated by a ','.

  * one single leaf name dictates that the data will be plotted on / next to / under the leaf or the branch connecting directly to the leaf node
  * two leaf names are often used in combination with an 'ad' at the third column; see the section 'third column' for more details.

For example:
  * chicken
  * mouse,human

### second column: color to be applied ###

### third column: optional commands to change the default behavior of current line ###
By default, the color will only apply to the specified leaf label; for example:

the tree:
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
## leaf background color<br>
mouse	red<br>
</pre>
</td><td>
<img src='https://www.evernote.com/shard/s130/sh/16cfca45-4a27-4f0b-8e91-7fe9ff383186/616179c9c839f22f0c502d3ae3e75918/res/1615093d-b41d-4a27-b6a8-4def78fd949e/skitch.png' />
</td></tr>
</table></blockquote>

By adding a third column, the default behavior can be changed. Here is a list of choices of this column:
| **Option** (case insensitive) | **Description** |
|:------------------------------|:----------------|
| ad                            | apply background color to the leaf labels of all descendants |
| prefix                        | apply background color to all leaf labels that start with the string specified by the first column |
| suffix                        | apply background color to all leaf labels that end with the string specified by the first column |
| anywhere                      | apply background color to leaf labels that contain the string specified by the first column |

For example:

<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr><td>
<blockquote><pre>
## leaf background color<br>
human,mouse	lightblue	ad<br>
</pre>
</td><td>
<img src='https://www.evernote.com/shard/s130/sh/de0e321a-a466-49ff-accd-96fe56af3943/a1713af3227f1b92028025da1c1dd671/res/ec8411e1-c751-4413-a924-29898686fcd7/skitch.png' />
</td></tr>
<tr><td>
<pre>
## leaf background color<br>
mouse,human	grey	ad<br>
ch	yellow	prefix<br>
</pre>
</td><td>
<img src='https://www.evernote.com/shard/s130/sh/1c2587f9-0595-4dcc-9cf3-a2a45dc7645b/2d80981fcbbdf87aad3c37c667715fd1/res/2762b683-8636-481d-b318-6a0cc81d24ef/skitch.png' />
</td></tr>
<tr><td>
<pre>
## leaf background color<br>
chicken,human	grey	ad<br>
n	blue	suffix<br>
</pre>
</td><td>
<img src='https://www.evernote.com/shard/s130/sh/a8b7dbb2-a449-4d21-9f21-458569a4159c/13e81bc60f07de06f6ffb0abfe2a2e96/res/b35b83ea-3b8c-4e21-8b7e-88e7442884f7/skitch.png' />
</td></tr></table>