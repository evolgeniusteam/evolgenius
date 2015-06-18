

## what's new ##

  * added new functionality **show data value** in bar plots, see section: [Show data value](EvolViewDatasetPieCharts#show_data_value.md). Here is an example plot:

![https://lh4.googleusercontent.com/-ff51XU2Ttjw/VChwjWl5LAI/AAAAAAAAAXE/9nG_qbjTyec/w779-h443-no/EvolView__project_-_DEMOS__tree_-_yeast_duplications.png](https://lh4.googleusercontent.com/-ff51XU2Ttjw/VChwjWl5LAI/AAAAAAAAAXE/9nG_qbjTyec/w779-h443-no/EvolView__project_-_DEMOS__tree_-_yeast_duplications.png)

## pie charts overview ##

**_NOTE_**

_please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._


Pies will be displayed on internal and leaf branches. Here is an example:

![https://lh4.googleusercontent.com/-9gYQorfNJco/UZu22IdksQI/AAAAAAAAAA4/XBeuhIkPEIw/w816-h413-no/skitch.png](https://lh4.googleusercontent.com/-9gYQorfNJco/UZu22IdksQI/AAAAAAAAAA4/XBeuhIkPEIw/w816-h413-no/skitch.png)

User can upload multiple pie-chart datasets to a tree, but only one can be displayed at a time. However user can control which one should be displayed using the control panel:

![https://lh6.googleusercontent.com/-w-MAXv4QtqE/UZu4rmH82yI/AAAAAAAAAB8/OFSbjW6nslI/w248-h102-no/skitch.png](https://lh6.googleusercontent.com/-w-MAXv4QtqE/UZu4rmH82yI/AAAAAAAAAB8/OFSbjW6nslI/w248-h102-no/skitch.png)


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
| _**pie charts specific**_  |           |                 |
| `!`minradius               | any float number > 0 | minimal pixel radius of the pies |
| `!`maxradius               | any float number > 0 | maximal pixel radius of the pies |
| `!`area                    | none      | use user inputs as the areas of the pie charts |
| `!`radius                  | none      | use user inputs as the radiuses of the pie charts |
| _**new: show data values**_ |  see section [show data value](EvolViewDatasetPieCharts#show_data_value.md) for more details  |                 |

## notes on preparing your dataset!! ##
**_NOTE:_**
  1. **please always use TAB to separate the modifiers and their values.**
  1. **some modifiers should not be used in combination, e.g. !area and !radius are mutually exclusive. However if both are used (accidentally), only the last one will be used.**
  1. **if a modifier is used (accidentally) multiple tiles, only the last one will be used.**
  1. **the "data" part of this dataset can only contain two columns of tab-delimited texts; the third column, if presents, will be ignored**

## some examples ##

The following we will provide you some examples. You can copy & paste the tree and datasets to EvolView to reproduce the results.

### the yeast duplication tree ###
1. the tree (in Newick format)
<pre>
((((((((((Saccharomyces_cerevisiae:0.054377,Saccharomyces_paradoxus:0.039196)Saccharomyces_subclade:0.035915,Saccharomyces_mikatae:0.082075)Saccharomyces_subclade:0.054132,Saccharomyces_bayanus:0.128022)Saccharomyces:0.485857,Candida_glabrata:0.874698)Saccharomycetaceae_subclade:0.060179,Naumovia_castellii:0.761269)Saccharomycetaceae_subclade:0.182516,(Lachancea_waltii:0.700985,(Kluyveromyces_lactis:0.770604,Agossypii:0.758273)Kluyveromyces:0.118441)Saccharomycetaceae_subclade:0.146942)Saccharomycetaceae:1.069627,(Debaryomyces_hansenii:0.591048,Candida_albicans:0.851762)Saccharomycetales_subclade:0.866539)Saccharomycetales_subclade:0.844816,Yarrowia_lipolytica:1.745091)Saccharomycetales:0.650477,(Emericella_nidulans:0.618015,(Magnaporthe_grisea:0.446021,(Neurospora_crassa:0.412753,Gibberella_zeae:0.414866)Sordariomycetes_subclade:0.071418)Sordariomycetes:0.318914)Pezizomycotina:0.873484)Ascomycota_subclade:0.955079,Schizosaccharomyces_pombe:0.952249);<br>
</pre>

2. dataset 1: "Duplication"

<pre>
## for evolview; Yeast<br>
!Groups	WGD,SSD<br>
!colors	#9F0251,#4D8963<br>
!legendstyle	circle<br>
!title	Duplication mechanism<br>
!opacity	0.8<br>
Saccharomyces_cerevisiae,Saccharomyces_paradoxus	0,19<br>
Saccharomyces_cerevisiae,Saccharomyces_mikatae	0,20<br>
Saccharomyces_cerevisiae,Saccharomyces_bayanus	0,18<br>
Saccharomyces_cerevisiae,Candida_glabrata	0,22<br>
Saccharomyces_cerevisiae,Naumovia_castellii	862,0<br>
Saccharomyces_cerevisiae,Lachancea_waltii	0,29<br>
Saccharomyces_cerevisiae,Candida_albicans	0,53<br>
Saccharomyces_cerevisiae,Yarrowia_lipolytica	0,26<br>
Saccharomyces_cerevisiae,Neurospora_crassa	0,169<br>
</pre>

**_important:_**
  1. an internal branch / node is identified by the names of two leaf nodes; the former is the last common ancestor of the latter
  1. the values of an internal branches are separated by ",", e.g. 0,19
  1. the number of values of all internal nodes should be the same (two in this dataset)
  1. the same number of colors should be provided by "!colors" ("#9F0251,#4D8963" in this case)
  1. and the same number of "groups" should also provided by "!groups"


![https://lh4.googleusercontent.com/-R-u24Mha6MI/UZu5CUHiHNI/AAAAAAAAACg/GWGO3uk7RZc/w579-h405-no/pie1.png](https://lh4.googleusercontent.com/-R-u24Mha6MI/UZu5CUHiHNI/AAAAAAAAACg/GWGO3uk7RZc/w579-h405-no/pie1.png)

3. dataset 2: overlap with other duplicates
<pre>
# for evolview; Yeast<br>
## created at may 25, 2011<br>
!Groups	WGD-O,WGD-N,SSD-O,SSD-N<br>
!colors	#9F0251,#f88ef9,#effc00,#4D8963<br>
!legendstyle	circle<br>
!title	overlap with other duplicates<br>
!opacity	0.8<br>
Saccharomyces_cerevisiae,Saccharomyces_paradoxus	0,0,24,14<br>
Saccharomyces_cerevisiae,Saccharomyces_mikatae	0,0,14,11<br>
Saccharomyces_cerevisiae,Saccharomyces_bayanus	0,0,13,16<br>
Saccharomyces_cerevisiae,Candida_glabrata	0,0,4,18<br>
Saccharomyces_cerevisiae,Naumovia_castellii	77,792,0,0<br>
Saccharomyces_cerevisiae,Lachancea_waltii	0,0,12,28<br>
Saccharomyces_cerevisiae,Candida_albicans	0,0,18,42<br>
Saccharomyces_cerevisiae,Yarrowia_lipolytica	0,0,11,16<br>
Saccharomyces_cerevisiae,Neurospora_crassa	0,0,28,143<br>
</pre>

![https://lh6.googleusercontent.com/-7xv0iAH4ZUQ/UZu5OpuSjjI/AAAAAAAAADE/Dwz_Q-Cf1Bs/w585-h397-no/pie2.png](https://lh6.googleusercontent.com/-7xv0iAH4ZUQ/UZu5OpuSjjI/AAAAAAAAADE/Dwz_Q-Cf1Bs/w585-h397-no/pie2.png)

## show data value ##

First, let's see an example using the same tree as above:

<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<blockquote><pre>
## for evolview; Yeast<br>
## by weihua chen; use Nature data<br>
## created at may 25, 2011<br>
!Groups	WGD-O,WGD-N,SSD-O,SSD_N<br>
!colors	#9F0251,#f88ef9,#effc00,#4D8963<br>
!legendstyle	rect<br>
!title	overlap with WGDs<br>
!opacity	0.8<br>
!showlegends	0<br>
!showDataValue	show=1,fontsize=12,fontcolor=darkblue,titalic=1<br>
Saccharomyces_cerevisiae,Saccharomyces_paradoxus	0,0,11,27<br>
Saccharomyces_cerevisiae,Saccharomyces_mikatae	0,0,0,25<br>
Saccharomyces_cerevisiae,Saccharomyces_bayanus	0,0,4,25<br>
Saccharomyces_cerevisiae,Candida_glabrata	0,0,2,20<br>
Saccharomyces_cerevisiae,Naumovia_castellii	869,0,0,0<br>
Saccharomyces_cerevisiae,Lachancea_waltii	0,0,0,40<br>
Saccharomyces_cerevisiae,Candida_albicans	0,0,9,51<br>
Saccharomyces_cerevisiae,Yarrowia_lipolytica	0,0,7,20<br>
Saccharomyces_cerevisiae,Neurospora_crassa	0,0,20,151<br>
</pre>
</td>
<td>
<img src='https://lh4.googleusercontent.com/-ff51XU2Ttjw/VChwjWl5LAI/AAAAAAAAAXE/9nG_qbjTyec/w779-h443-no/EvolView__project_-_DEMOS__tree_-_yeast_duplications.png' />
</td></tr>
</table></blockquote>

The 'value' of the 'key' _**!showdataValue**_ can be any combination of the following, separated by a ",":

|  | **alternative value** | **description** |
|:-|:----------------------|:----------------|
| show = 1 | 0                     | show or hide data values; optional; the data values will be shown if omitted |
| fontsize=12 | any integer           | set font size; optional; default = 10 |
| fontcolor=red | any value color name  | set text color; optional; default = black |
| fontitalic=1 | 0                     | set font italic; optional; default = 0 |


## more examples to be added ##