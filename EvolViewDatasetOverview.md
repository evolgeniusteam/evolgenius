## A dataset typically consists of three sections ##

  1. annotation,
  1. modifiers and
  1. data

For example:

<pre>
## -- here is an example dataset of a barplot; lines start with # are annotations and will not be parsed by EvolView --<br>
## -- the following are the modifiers --<br>
## -- please use TAB to separate the modifiers and their values<br>
!legendText	group 1,group 2,group 3<br>
!legendTitle	Example of barplots<br>
!legendStyle	circle<br>
!colors	#028482,#7ABA7A,#B76EB8<br>
!plotwidth	200<br>
## -- annotation can be also put here --<br>
## -- here comes the data --<br>
## -- please use TAB to separate the columns --<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>

![https://lh3.googleusercontent.com/-cS2wPz9BY9Q/UahvZekRKWI/AAAAAAAAAOI/AFtxkQZqzoE/w547-h249-no/skitch2.png](https://lh3.googleusercontent.com/-cS2wPz9BY9Q/UahvZekRKWI/AAAAAAAAAOI/AFtxkQZqzoE/w547-h249-no/skitch2.png)

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

**_please always use TAB to separate the modifiers and their values!!_**

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

#### third column: optional commands to change the default behavior of the input ####


in this case, an 'ad' dictates that the branches of not only the common ancestor of human and mouse, but also all descendents (ad) the common ancestor will be colored in red.

**_please always use TAB to separate the columns._**

## So far the following datasets are supported ##
  1. [Pie charts](EvolViewDatasetPieCharts.md)
  1. [Bars](EvolViewDatasetBars.md)
  1. [Branch color](EvolViewDatasetBranchColor.md)
  1. [Leaf color](EvolViewDatasetLeafColor.md)
  1. [Leaf background color](EvolViewDatasetLeafBKColor.md)
  1. [Color strip and color shapes](EvolViewDatasetColorStrip.md)
  1. [Protein domains](EvolViewProteinDomain.md)
  1. [Leaf label decorations](EvolViewDatasetLeafDecoration.md)
  1. [Group labels](EvolViewDatasetGroupLabels.md)
  1. [Dot Plots](EvolViewDatasetDotplots.md)
  1. [Heatmap](EvolViewDatasetHeatmap.md)