

## leaf colors overview ##

**_NOTE_**

_please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._

Leaf colors will change the colors of leaf labels. Similar to branch colors, multiple datasets can be uploaded to a tree, but only one can be shown at a time.

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

Again, we use the same tree as example:
```
(chicken,((mouse,rat),(chimp,human)));
```

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
## leaf color<br>
human	red<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/1ec434f3-ab2a-4b35-b4ba-9af2364417bc/623980dcf1647a28ecd4a22ebd36a068/res/c50b32d7-9850-43fd-8dcb-7821c44faae0/skitch.png' />
</td></tr>
</table></blockquote>

By adding a third column, the default behavior can be changed. Here is a list of choices of this column:
| **Option** (case insensitive) | **Description** |
|:------------------------------|:----------------|
| ad                            | apply color to the leaf labels of all descendants |
| prefix                        | apply color to all leaf labels that start with the string specified by the first column |
| suffix                        | apply color to all leaf labels that end with the string specified by the first column |
| anywhere                      | apply color to leaf labels that contain the string specified by the first column |

For example:

<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr><td>
<blockquote><pre>
## leaf color<br>
human,mouse	pink	ad<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/d50cd521-0475-491e-8ab2-916534abce01/ff87e9b5c6acb0701de7c0733fd225ef/res/7eb838a3-f0bb-455d-9ead-d667bb4a1dbf/skitch.png' />
</td></tr>
<tr><td>
<pre>
## leaf color<br>
ch	yellow	prefix<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/932e2d6b-b098-4ae5-889e-be2eb6b7a537/c2316a5c866e33ce821922378cb06435/res/54b926e4-7028-488a-bd38-a8140c6cd3c7/skitch.png' />
</td></tr>
<tr><td>
<pre>
## leaf color<br>
n	blue	suffix<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/dbe7587a-d0f1-46c0-9fd9-22d338f04e7f/ae3d34482a46846c1bfab4a69369d45a/res/34ada58d-268f-4d54-95b4-edb2bd6acd19/skitch.png' />
</td></tr>
<tr><td>
<pre>
## leaf color<br>
m	purple	anywhere<br>
</pre>
</td>
<td>
<img src='https://www.evernote.com/shard/s130/sh/6fbfaf4d-0862-4a43-a2b5-fda78590f0a8/c7dc776d49c5728005c0155a2c2c65e9/res/cb0f9421-9667-482e-87cb-fa8ae2c79f9d/skitch.png' />
</td></tr>
</table>