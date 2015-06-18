## Stroke colour and width ##

**_NOTE_**

_please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._

One potential use of stroke colour is to make hollowed shapes like the following:

![https://lh6.googleusercontent.com/-jvVCcDS3cks/U0zs20Ohy1I/AAAAAAAAARQ/xOnr6Q9Ku58/w236-h128-no/EvolView___my_projects_and_trees.png](https://lh6.googleusercontent.com/-jvVCcDS3cks/U0zs20Ohy1I/AAAAAAAAARQ/xOnr6Q9Ku58/w236-h128-no/EvolView___my_projects_and_trees.png)

The tree:

```
(A:0.1,B:0.2,(C:0.3,D:0.4)100:0.5)90:0.43;
```

The dataset (colour shapes and strips):
<table border='0'>
<tr>
<td>
<pre>
##color strips<br>
!defaultstrokewidth	1<br>
<br>
!type	rect,star,triangle,rect<br>
!showlegends	0<br>
A	white:grey,white:blue<br>
B	white:red<br>
C	white:grey<br>
D	white:red<br>
</pre>
</td>
</tr>
</table>

In EvolView, the colour attribute of an object can be written as :
```
fill_color[:stroke_color]
```
When the stroke\_color is omitted, no stroke will be drawn.

### default stroke width ###
By default, a stroke width of '1' (one pixel) will be used; this can be changed by using a modifier:
```
!defaultStrokeWidth    stroke_width_value
```
Note this value will be applied to all shapes.

### default stroke color ###
A default colour can also be specified by the following modifier:
```
!defaultStrokeColor   valid_stroke_color
```
and it will be applied to shapes without user-supplied stroke colours.

### more examples ###
The following are more examples:
<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<pre>
##color strips<br>
!defaultstrokewidth	2<br>
!type	rect,circle,star,triangle<br>
!showlegends	1<br>
A	red,green,blue:red<br>
B	purple,darkred,lightgreen<br>
C	lightblue<br>
D	darkgreen,grey,pink<br>
<br>
</pre>
</td>

<td>
<img src='https://lh4.googleusercontent.com/-qtqj7Hu0Hvg/U0zzmFxoosI/AAAAAAAAAR8/059IuaMIbg8/w533-h195-no/EvolView___my_projects_and_trees.png' />

</td>
</tr>
<tr>
<td>
<pre>
##color strips<br>
!defaultstrokewidth	2<br>
!defaultstrokecolor	gold<br>
!type	rect,circle,star,triangle<br>
!showlegends	1<br>
A	red,green,blue:red<br>
B	purple,darkred,lightgreen<br>
C	lightblue<br>
D	darkgreen,grey,pink<br>
<br>
</pre>
</td>

<td>
<img src='https://lh6.googleusercontent.com/-88kDoZGmmwA/U0z0hQBAO6I/AAAAAAAAASc/IHU7sjgF1Lg/w540-h178-no/EvolView___my_projects_and_trees.png' />
</td>
</tr>

<tr>
<td>
<pre>
## a bar plot<br>
!groups	group 1,group 2,group 3<br>
!colors	#028482,#7ABA7A:red,#B76EB8<br>
!align<br>
!itemHeightPCT	60<br>
A	8,13,5<br>
B	10,20,7<br>
C	8,9,7<br>
D	20,5,20<br>
</pre>
</td>

<td>
<img src='https://lh5.googleusercontent.com/-Q0UYVsgcex8/U0z1kp_nAjI/AAAAAAAAATE/GgTB00GDHL4/w405-h199-no/EvolView___my_projects_and_trees.png' />
</td>
</tr>

</table>

Have fun!!