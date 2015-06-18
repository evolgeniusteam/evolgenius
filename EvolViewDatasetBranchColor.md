

## branch colors overview ##

**_NOTE_**

_please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._

Branch colors will be applied to tree branches. Similar to pie charts, multiple datasets for branch colors can be uploaded to a tree, but only one can be shown at a time.

Here is an example:
![https://lh5.googleusercontent.com/--LA0DMV_SSU/UaccaqHczLI/AAAAAAAAAJw/dJLpWR9lH3o/w829-h711-no/ev.branch.001.png](https://lh5.googleusercontent.com/--LA0DMV_SSU/UaccaqHczLI/AAAAAAAAAJw/dJLpWR9lH3o/w829-h711-no/ev.branch.001.png)

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

Here we use the tree:
```
(chicken,((mouse,rat),(chimp,human)));
```

### first column: the location ###
the first column dictates where the data to be plotted. It usually contains the name of a leaf node, or two leaf names separated by a ','.

  * one single leaf name dictates that the data will be plotted on / next to / under the leaf or the branch connecting directly to the leaf node
  * two leaf names, on the hand, dictates that the data will be displayed on the branch representing the last common ancestor of the two leaf nodes

For example:
  * chicken
  * mouse,human

### second column: color to be applied ###

### third column: optional commands to change the default behavior of current line ###
By default, the color will only apply to the specified branch; for example:
<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<blockquote><pre>
## branch color/ styles<br>
human	red<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/eb96d28c-6588-4489-8567-9cf875f52ed3/b007594bfb43eedbce2b541d972312d7/res/83eff3ef-ddbb-4084-a1d6-9d86c7d52542/skitch.png' />
</td>
</tr>
</table></blockquote>


By adding a third column, the default behavior can be changed. Here is a list of choices of this column:
| **Option** (case insensitive) | **Description** |
|:------------------------------|:----------------|
| ad                            | apply color to all descendants |
| prefix                        | apply color to all branches connecting leaf nodes whose name starts with the string specified by the first column |
| suffix                        | apply color to all branches connecting leaf nodes whose name ends with the string specified by the first column |
| anywhere                      | apply color to all branches connecting leaf nodes whose name contains the string specified by the first column |
| toroot                        | apply color to all branches connecting the leaf node and parent nodes all the way to the root |

See examples bellow:
<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<blockquote><pre>
## branch color<br>
human,mouse	red	ad<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/9aa107e7-dda5-43dc-bb12-959393006fbf/1024a2bea6bc99145616028a90c9a784/res/72c62775-ac94-4542-a349-c639079226e5/skitch.png' />
</td></tr>
<tr><td>
<pre>
## branch color<br>
ch	red	prefix<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/c5905460-209b-406f-9256-c2e4b2bbb5a7/671e853824d0e8922381580168fcb874/res/4531a011-9561-42d5-80fc-06b4a65587d0/skitch.png' />
</td></tr></blockquote>

<tr><td>
<blockquote><pre>
## branch color<br>
n	red	suffix<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/9b8435a6-ef21-4f3d-9ffc-3b84ead79bf0/2d9330c9252e276f5431e335ef57d3f6/res/8b844c94-9f96-497f-b3f1-8a2211c4f19c/skitch.png' />
</td>
</tr></blockquote>

<tr><td>
<blockquote><pre>
## branch color from specified leaf node to the root<br>
human	red	toroot<br>
</pre>
</td>
<td>
<img src='https://lh3.googleusercontent.com/-qcACUqEbttE/U6GmW5oQLzI/AAAAAAAAAWI/oe71SEMuImo/w219-h191-no/Screen+Shot+2014-06-18+at+16.45.27.png' />
</td>
</tr></blockquote>

</table>