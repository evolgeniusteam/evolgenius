

## A dataset typically consists of three sections ##

A dataset typically contains three sections, annotation, modifiers and data; for example:

### Annotations ###

Lines with the first character as '#' are annotations. Annotations are usually at the beginning of a dataset; however if desired, annotation lines can be placed anywhere in a dataset.

### Modifiers / Key-Attribute pairs ###
KA - pairs usually start with '!', and are separated by a single 'tab' character; KA pairs are used to specify or change certain default settings / behavior of a dataset, for example:
  * to set the title or legend
  * to change the width, height or opacity of the dataset
in some cases, the attribute part of a KA-pair is optional.

Here are a list of KA-pairs common to all datasets; dataset-specific KA-pairs will be introduced later.

| **Key** (case insensitive) | **Value** | **Description** |
|:---------------------------|:----------|:----------------|
| `!`Groups or `!`LegendText |comma separated text| Legend texts; for example 'group\_a,group\_b,group\_c'|
| `!`LegendStyle or `!`Style  | rect or circle or star | shapes to be plotted before the legend texts; default = rect |
| `!`LegendColors or `!`Colors |comma separated color codes or names| colors to be applied to the shapes specified by LegendStyle; for example 'red,green,yellow' ; note the number of colors should match the number of legend fields|
| `!`Title or `!`Legend      | text      | title of the legend; default = name of the dataset |
| `!`ShowLegends             | 0 or 1    | 0 : hide legends; 1 : show legends |
| `!`opacity                 | float number between 0 to 1 | opacity of the dataset |
| `!`PlotWidth               | integer > 0 | pixel width of the dataset on canvas |

See the picture bellow:
[pic](pic.md)

### Data ###
Data are usually tab-delimited three-column texts, with the third column optional.

#### first column: the location ####
the first column dictates where the data to be plotted. It usually contains the name of a leaf node, or two leaf names separated by a ','.

  * one single leaf name dictates that the data will be plotted on / next to / under the leaf or the branch connecting directly to the leaf node
  * two leaf names, on the hand, dictates that the data will be displayed on the branch representing the last common ancestor of the two leaf nodes

For example:
  * chicken
  * mouse,human

#### second column: data to be displayed ####

#### third column: optional commands to change the default behavior of ## ####


in this case, an 'ad' dictates that the branches of not only the common ancestor of human and mouse, but also all descendents (ad) the common ancestor will be colored in red.

## So far there are in total six types of datasets ##
### pie charts ###

Additional Key-Value pairs for pie charts:
| **Key** (case insensitive) | **Value** | **Description** |
|:---------------------------|:----------|:----------------|
| `!`minradius               | any float number > 0 | minimal pixel radius of the pies |
| `!`maxradius               | any float number > 0 | maximal pixel radius of the pies |
| `!`area                    | none      | use user inputs as the areas of the pie charts |
| `!`radius                  | none      | use user inputs as the radiuses of the pie charts |

**_Please note:_**
  * the "data" part of this dataset can only contain two columns of tab-delimited texts; the third column, if presents, will be ignored

Examples (to be added)

### bars ###
Additional Key-Value pairs for bar plots:
| **Key** (case insensitive) | **Value** | **Description** |
|:---------------------------|:----------|:----------------|
| `!`align or `!`alignIndividualColumn | none      | align individual columns if the bars are stacked |
| `!`grid                    | none      | show a background grid |
| `!`gridlabel or `!`axis    | none      | show the values corresponding to the grid lines |
| `!`Fanplot or `!` Fan      | none      | see examples bellow |

**_Please note:_**
  * in the "data" part of the dataset, only the first two columns will be used;
  * the number groups (!groups, comma separated) must match the number of colors (!colors); both must match the number of the numeric data (common separated) in each line of the "data" section

#### Examples ####
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
<img src='http://img.skitch.com/20111122-j3cddm2sydmq7ebnia8e46ix4j.png' />
</td></tr>
<tr><td>
<pre>
## turn grid on<br>
!grid<br>
</pre>
</td>
<td><img src='http://img.skitch.com/20111122-fnu17e36jqkhb9ued9u9fcukwq.png' />
</td></tr>
<tr><td>
<pre>
## turn grid on<br>
## align individual columns<br>
!grid<br>
!align<br>
</pre>
</td><td>
<img src='http://img.skitch.com/20111122-e6icdairtb4xn9wgrii1pux2gb.png' />
</td></tr>
<tr><td>
<pre>
## fan plot of the bars in circular mode<br>
!fan<br>
</pre>
</td><td>
<img src='http://img.skitch.com/20111122-p5r9rid311qn72kn8cy6k6h5yt.png' />
</td></tr>
<tr><td>
<pre>
## fan plot of the bars in circular mode<br>
## and align individual columns<br>
!fan<br>
!align<br>
</pre>
</td><td>
<img src='http://img.skitch.com/20111122-nfywwbncdtuwg2jbk52t7gj8y3.jpg' />
</td></tr>
</table></blockquote>

### Branch colors ###
Additional Key-Value pairs for branch style (to be implemented):
| **Key** (case insensitive) | **Value** | **Description** |
|:---------------------------|:----------|:----------------|
| `!`LineWidth or `!`Lwd     | float number > 0 | set / change the line width |
| `!`Linestyle               | dot | dotted | dash | dashed | set / change the line style |

#### use the third column of the data section to change the default behaviors ####
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
<img src='https://img.skitch.com/20111209-dtewi11mqwdc1e7ntw265bd77c.png' />
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

See examples bellow:

#### examples ####
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
<img src='https://img.skitch.com/20111209-mnrcqfpkjx3371jwgjsr5krr3d.png' />
</td></tr>
<tr><td>
<pre>
## branch color<br>
ch	red	prefix<br>
</pre>
</td>
<td>
<img src='https://img.skitch.com/20111209-pa62nursj8hnieeumcpa3b7ui6.png' />
</td></tr>
<tr><td>
<pre>
## branch color<br>
n	red	suffix<br>
</pre>
</td>
<td>
<img src='https://img.skitch.com/20111209-pabkud25y3siysdk7y5wx58r1.png' />
</td></tr></table></blockquote>

### leaf colors ###
#### Examples ####
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
<img src='https://img.skitch.com/20111209-tbt68i3yj77ap3b1nkgxaiy655.png' />
</td></tr>
<tr><td>
<pre>
## leaf color<br>
human,mouse	pink	ad<br>
</pre>
</td>
<td>
<img src='https://img.skitch.com/20111209-tkpbhtimewydsn1dydduk5gg5a.png' />
</td></tr>
<tr><td>
<pre>
## leaf color<br>
ch	yellow	prefix<br>
</pre>
</td>
<td>
<img src='https://img.skitch.com/20111209-qwcuf838f5imc1ceyk77wqf7in.png' />
</td></tr>
<tr><td>
<pre>
## leaf color<br>
n	blue	suffix<br>
</pre>
</td>
<td>
<img src='https://img.skitch.com/20111209-rergxsq22t59bg83ewnbqmc12m.png' />
</td></tr>
<tr><td>
<pre>
## leaf color<br>
m	darkblue	anywhere<br>
</pre>
</td>
<td>
<img src='https://img.skitch.com/20111209-rxgxyi3un4krgqi7c1km5r4usd.png' />
</td></tr>
</table></blockquote>

### background colors for leaf labels ###
#### examples ####
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
<img src='https://img.skitch.com/20111209-g27erp3hhnn74wb8eyujfuhmpi.png' />
</td></tr>
<tr><td>
<pre>
## leaf background color<br>
human,mouse	lightblue	ad<br>
</pre>
</td><td>
<img src='https://img.skitch.com/20111209-dg9jy8jhd182fim1x4hb8edqac.png' />
</td></tr>
<tr><td>
<pre>
## leaf background color<br>
mouse,human	grey	ad<br>
ch	yellow	prefix<br>
</pre>
</td><td>
<img src='https://img.skitch.com/20111209-j95db7k4mqqcyqwn9tphp95khu.png' />
</td></tr>
<tr><td>
<pre>
## leaf background color<br>
chicken,human	grey	ad<br>
n	blue	suffix<br>
</pre>
</td><td>
<img src='https://img.skitch.com/20111209-cmka8ej3jhuha4ik4extsqerkx.png' />
</td></tr></table></blockquote>

### color strips / color shapes ###
#### examples ####
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
<img src='https://img.skitch.com/20111209-8783r2t362pb83mfdnr6tdi72.png' />
</td></tr></table>