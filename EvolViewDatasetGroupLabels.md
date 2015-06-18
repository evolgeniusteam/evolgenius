

**_NOTE_**

  * _please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._
  * please consult our examples trees 'group label', 'group label style 3' and 'group label style 4' in the DEMOS project

## Group Labels overview ##

Group labels will be displayed next to the leaf labels, therefore:
  * it falls into the 'Charts' category, and
  * multiple Group Labels datasets can be displayed at the same time (unlike pies, users can upload multiple pies datasets, but only one dataset can be displayed at a time).

Here is an quick example (display style 1 out of in total **5** styles ):

![https://www.evernote.com/shard/s130/sh/f748fcac-09eb-4821-9d6d-bda950524daf/dfde7396818b2c69e041a75dc1cccf1c/res/5c406888-67d1-432b-8676-47a5a8dfbc20/skitch.png](https://www.evernote.com/shard/s130/sh/f748fcac-09eb-4821-9d6d-bda950524daf/dfde7396818b2c69e041a75dc1cccf1c/res/5c406888-67d1-432b-8676-47a5a8dfbc20/skitch.png)

Here is the tree:

`(chicken,((mouse,rat),(chimp,human)));`

And the dataset:
<table border='1'>
<tr>
<th>Dataset</th>
</tr>
<tr>
<td>
<blockquote><pre>
!grouplabel	color=pink,show=1,fontsize=14,fontcolor=black,fontitalic=0,textalign=middle,textorientation=horizontal,linewidth=2<br>
chicken	  text=cute by itself,fontcolor=red,linewidth=4<br>
mouse,rat	text=rodent,linecolor=darkgrey,fontcolor=purple,linestyle=dashed,textalign=middle<br>
chimp,human	text=mammal,color=darkgreen,textorientation=vertical,linewidth=4,fontsize=16<br>
</pre>
</td></tr></table></blockquote>

### Supported modifiers ###
Apart from the common modifiers such as those that are related to legends ([see here for an overview](https://code.google.com/p/evolgenius/wiki/EvolViewDatasetOverview)), Group Labels supports an additional modifier: **!groupLabel**.

The _value_ of this modifier defines default settings for all group labels and can be any combination of the following, separated by a ",":
|  | **alternative value** | **description** |
|:-|:----------------------|:----------------|
| show=1 | 0                     | show or hide group labels; optional; the data values will be shown if omitted |
| style=1| any integer from 1 to 5 | visualization style of group labels; see the following section for more examples; default is 1 |
| color=pink | any color name or valid html hex colors such as #FF0000 | default color for group lines and labels; default = black |
| linewidth=2 | any integer >= 0      | set width of the group line; default = 1; if set to 0, the group line is hidden; **valid only when style=1**; see examples bellow |
| linestyle=dashed |                       | if set, a dotted group line will be plotted; default is regular line; **valid only when style=1**; see examples bellow |
| fontcolor=black | any color name or valid html hex colors such as #FF0000 | default color of group labels; default = black; if omitted, uses 'color' |
| fontsize=12 | any integer           | set font size; optional; default = 10 |
| fontitalic=1 | 0                     | set font italic; optional; default = 0 |
| textalign=middle | start or end          | set text align; optional; default = middle; see the following examples |
| textorientation=horizontal | vertical              | set text orientation relative to leaf label; default = horizontal; see examples bellow |
| bkcolor=colorname | any color name or valid html hex colors such as #FFFF00 | default color for group background; **valid only when style = 2~5**; default = lightblue |
| marginPCT=0.05 | any float value between 0 and 1 |  white space between group labels; the larger the value, the more white space to show; default = 0.05 |

### Data ###
Each line of the Data section usually consists two parts, separated by a TAB.

The first part defines to where the group label will be placed, it can be either:
  * names of two leaf labels, separated by a ',', or
  * a name of a leaf label.

The second part specifics the 'label' (required) and optional settings for this label such as font color, size.

See bellow:

![https://lh5.googleusercontent.com/-BjBbtkifP3M/VI6YWrVu_lI/AAAAAAAAAb4/b6xlPqdzXyI/w721-h159-no/Edit_EvolViewDatasetGroupLabels_-_evolgenius_-_Genius_ways_to_perform_evolutionary_analyses_-_Google_Project_Hosting.png](https://lh5.googleusercontent.com/-BjBbtkifP3M/VI6YWrVu_lI/AAAAAAAAAb4/b6xlPqdzXyI/w721-h159-no/Edit_EvolViewDatasetGroupLabels_-_evolgenius_-_Genius_ways_to_perform_evolutionary_analyses_-_Google_Project_Hosting.png)

### Visualization styles ###

_**copy & paste the datasets to your tree to see the results**_

Let's first showcase the the rest four visualization styles:

<table border='1'>
<tr><th>Dataset</th><th>Plot</th></tr>

<tr> <td> <b> style=2 </b> </td> </tr>

<tr>
<td>
<blockquote><pre>
!grouplabel	style=2,color=pink,show=1,marginPCT=0.05,fontsize=14,fontcolor=white,fontitalic=0,textalign=middle,textorientation=horizontal,linewidth=2<br>
!op	0.8<br>
chicken	bkcolor=#404AC3,text=chicken<br>
mouse,rat	bkcolor=green,text=rodent,fontcolor=darkred<br>
chimp,human	bkcolor=#BE4144,text=mammal,textorientation=vertical,linewidth=4,fontsize=16<br>
</pre>
</td></blockquote>

<td>
<img src='https://www.evernote.com/shard/s130/sh/8b08dc8c-ac57-49a2-8399-1edb8507d6dd/3f28630991149d479c7cfa3a027ea7b4/res/c1226bac-017d-4b46-af6c-f6a83d664b4b/skitch.png' />
</td>

</tr>

<tr> <td> <b> style=3; here the background color box will start at the position of the last common ancestor of the specified leaf nodes </b> </td> </tr>

<tr><td>

<pre>
!grouplabel	style=3,color=pink,show=1,marginPCT=0.05,fontsize=14,fontcolor=white,fontitalic=0,textalign=middle,textorientation=horizontal,linewidth=2<br>
!op	0.8<br>
chicken	bkcolor=#404AC3,text=chicken<br>
mouse	bkcolor=green,text=rodent,fontcolor=darkred<br>
rat,human	bkcolor=#BE4144,text=mammal,textorientation=vertical,linewidth=4,fontsize=16<br>
</pre>
</td>

<td>
<img src='https://www.evernote.com/shard/s130/sh/0087e56a-7619-43b9-91e2-954d887797ad/0f6ba85ee2bd7f41abe509b34c8fb706/res/33f41a1f-e217-44ad-969b-a53bca51b83e/skitch.png' />
</td>
</tr>


<tr> <td> <b> style=4; here the background color box will start before the root </b> </td> </tr>

<tr><td>

<pre>
!grouplabel	style=4,color=pink,show=1,marginPCT=0.05,fontsize=14,fontcolor=white,fontitalic=0,textalign=middle,textorientation=horizontal,linewidth=2<br>
!op	0.8<br>
chicken	bkcolor=#404AC3,text=chicken<br>
mouse	bkcolor=green,text=rodent,fontcolor=darkred<br>
rat,human	bkcolor=#BE4144,text=mammal,textorientation=vertical,linewidth=4,fontsize=16<br>
</pre>
</td>

<td>
<img src='https://www.evernote.com/shard/s130/sh/76d4bc00-a040-4043-b9ea-1e8e915c584c/30189684be40c0a423d474b1f414ba3f/res/506a9c1b-faa6-4541-b62c-9ebbad86199e/skitch.png' />
</td>
</tr>

<tr> <td> <b> style=5; here the group labels will be drawn on the left of the tree; in circular mode this wouldn't work so it'll be plotted as style = 4  </b> </td> </tr>

<tr><td>

<pre>
!grouplabel	style=5,color=pink,show=1,marginPCT=0.05,fontsize=14,fontcolor=white,fontitalic=0,textalign=middle,textorientation=horizontal,linewidth=2<br>
!op	0.8<br>
chicken	bkcolor=#404AC3,text=chicken<br>
mouse	bkcolor=green,text=rodent,fontcolor=darkred<br>
rat,human	bkcolor=#BE4144,text=mammal,textorientation=vertical,linewidth=4,fontsize=16<br>
</pre>
</td>

<td>
<img src='https://www.evernote.com/shard/s130/sh/430214d8-0f05-41d3-ba34-ba0a73a510d2/6e3ce7810b2c8125f3d5a1758f358a0b/res/1360fdde-eef6-49de-be23-37201b573cf5/skitch.png' />
</td>
</tr>

</table>

In circule mode:

![https://www.evernote.com/shard/s130/sh/f7767d62-cec7-434f-a15f-fe436175a0e3/a649b2bb48c2e37fba2b435d0317e21a/res/db398b32-f703-411b-b8fc-923516f14831/skitch.png](https://www.evernote.com/shard/s130/sh/f7767d62-cec7-434f-a15f-fe436175a0e3/a649b2bb48c2e37fba2b435d0317e21a/res/db398b32-f703-411b-b8fc-923516f14831/skitch.png)

### more examples ###


<table border='1'>
<tr> <th>Dataset</th> <th>Plot</th></tr>
<tr>
<td>
<blockquote><pre>

chicken	  text=cute by itself<br>
mouse,rat	text=rodent<br>
chimp,human	text=mammal<br>
</pre>
</td>
<td>
<img src='https://lh5.googleusercontent.com/-sFSaBg3mBrE/VI6kRwGGoiI/AAAAAAAAAck/1Cr73k13QdM/w284-h273-no/EvolView__project_-_Admin__tree_-_group_label.png' />
</td></tr>
<tr><td></blockquote>

<pre>
# group label ; color applies to both the group labels and lines ...<br>
!GroupLabel	color=red<br>
chicken	  text=cute by itself<br>
mouse,rat	text=rodent<br>
chimp,human	text=mammal<br>
</pre>

</td>
<td>
<img src='https://lh6.googleusercontent.com/-WgsMUXsTw1A/VI6kTLLg3II/AAAAAAAAAcs/6yExLp3B2pE/w292-h234-no/EvolView__project_-_Admin__tree_-_group_label.png' />
</td></tr>
<tr><td>

<pre>
# group label ; now use a different color for the font; html hex color is also supported<br>
!GroupLabel	color=red,fontcolor=#0000FF<br>
chicken	  text=cute by itself<br>
mouse,rat	text=rodent<br>
chimp,human	text=mammal<br>
</pre>

</td><td>
<img src='https://lh6.googleusercontent.com/-d3Ic9IoKcns/VI6kVTDlSfI/AAAAAAAAAc0/cvdkCul3pnc/w286-h231-no/EvolView__project_-_Admin__tree_-_group_label.png' />
</td></tr>
<tr><td>

<pre>
# group label ; a more complicated example<br>
!GroupLabel	color=red,fontcolor=#0000FF,fontsize=20,fontitalic=1,textalign=start,textorientation=horizontal,linewidth=2<br>
chicken	  text=cute by itself<br>
mouse,rat	text=rodent<br>
chimp,human	text=mammal<br>
</pre>

</td><td>
<img src='https://lh4.googleusercontent.com/-UBIKDKl-1s0/VI6kXT3zLAI/AAAAAAAAAc8/ocsysQV9H80/w332-h240-no/EvolView__project_-_Admin__tree_-_group_label.png' />
</td></tr>

<tr> <td> <b> ###  textalign=start|end|middle ### </b> </td> </tr>

<tr><td>
<pre>
## by default group labels are placed at the middle of the group line; the positions can be<br>
## specified using textalign with one of the three options: start, end or middle<br>
!GroupLabel	textalign=end<br>
chicken	  text=cute by itself<br>
mouse,rat	text=rodent<br>
chimp,human	text=mammal<br>
</pre>

</td><td>
<img src='https://lh4.googleusercontent.com/-7-6eCCR1kLo/VI6kYt5DCQI/AAAAAAAAAdE/jCk31EGwtjQ/w283-h233-no/EvolView__project_-_Admin__tree_-_group_label.png' />
</td></tr>

<tr> <td> <b> ###  textorientation=horizontal|vertical ; NOTE the difference with 'textalign' ### </b> </td> </tr>

<tr><td>
<pre>
## -- textorientation specifies the orientation of group labels relative to leaf labels<br>
!GroupLabel	textorientation=vertical<br>
chicken	  text=cute by itself<br>
mouse,rat	text=rodent<br>
chimp,human	text=mammal<br>
</pre>
</td><td>
<img src='https://lh3.googleusercontent.com/-5X4r3e-ACxM/VI6kaCYNOTI/AAAAAAAAAdM/YhXte2UO5ag/w333-h342-no/EvolView__project_-_Admin__tree_-_group_label.png' />
</td></tr>

<tr><td>
<pre>
## -- textorientation can be used in combination with textalign --<br>
!GroupLabel	textalign=end,textorientation=vertical<br>
chicken	  text=cute by itself<br>
mouse,rat	text=rodent<br>
chimp,human	text=mammal</pre>
</td><td>
<img src='https://lh3.googleusercontent.com/-2AJe6zw4OWE/VI6kgCD6NNI/AAAAAAAAAdU/d9BHv_PqfZY/w315-h332-no/EvolView__project_-_Admin__tree_-_group_label.png' />
</td></tr>

<tr> <td> <b> ### use linewidth and linestyle to change the looks of group lines   #### </b> </td> </tr>

<tr><td>
<pre>
!GroupLabel	linewidth=10,linestyle=dashed,color=red,fontcolor=black<br>
chicken	  text=cute by itself<br>
mouse,rat	text=rodent<br>
chimp,human	text=mammal<br>
</pre>
</td><td>
<img src='https://lh3.googleusercontent.com/-2iDrXU944Kk/VI6kjHsbeRI/AAAAAAAAAdk/Q2fVzcQdn3o/w282-h279-no/EvolView__project_-_Admin__tree_-_group_label.png' />
</td></tr>

<tr> <td> <b> ## by default, the settings in GroupLabel will be applied to all group labels, however, they could be overridden by local settings </b> </td> </tr>

<tr><td>
<pre>
!grouplabel	color=pink,show=1,fontsize=14,fontitalic=0,textalign=middle,textorientation=horizontal,linewidth=2<br>
chicken	text=cute by itself,linewidth=4<br>
mouse,rat	text=rodent,linecolor=darkgrey,fontcolor=purple,linestyle=dashed,textalign=middle<br>
chimp,human	text=mammal,color=darkgreen,textorientation=vertical,linewidth=4,fontsize=16,textalign=end<br>
</pre>
</td><td>
<img src='https://lh3.googleusercontent.com/-GUpAVHEAy1I/VI6kkl93gPI/AAAAAAAAAds/CH7ctFQ1pso/w345-h400-no/EvolView__project_-_Admin__tree_-_group_label.png' />
</td></tr>


<tr> <td> <b> ## change margin using marginPCT (case insensitive) </b> </td> </tr>

<tr><td>
<pre>
!grouplabel	marginPCT=0.01<br>
</pre>
</td><td>
<img src='https://www.evernote.com/shard/s130/sh/7ee9b6c8-a4a6-4087-9c4d-871565c69b42/4d255a01f639c0db37c6e70e1b3eb05f/res/e9d1d846-247d-4d03-b09d-95f808f15dac/skitch.png' />
</td></tr>



</table>