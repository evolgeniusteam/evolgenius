

## leaf label decoration overview ##

**_NOTE_**

_please send email to us (evolgenius.team@gmail.com) if you have any questions; attach your datasets and trees if necessary._

Leaf decorations are colour objects / shapes to be shown between the leaf node labels and branches:

![https://lh5.googleusercontent.com/-tIvPNvumrvs/U00EJJIByPI/AAAAAAAAAT4/_zD-FHislnI/w165-h131-no/EvolView___my_projects_and_trees.png](https://lh5.googleusercontent.com/-tIvPNvumrvs/U00EJJIByPI/AAAAAAAAAT4/_zD-FHislnI/w165-h131-no/EvolView___my_projects_and_trees.png)

The tree:
```
(A:0.1,(B:0.2,(C:0.3,D:0.4)100:0.05)100:0.1)90:0.43;
```

and the data (leaf label decorations):
<table border='0'>
<tr>
<td>
<pre>
!defaultstrokewidth	0.7<br>
A	triangle,red:red<br>
B	triangle,white:red<br>
C	triangle,white:green<br>
D	triangle,green:green<br>
</pre>
</td>
</tr>
</table>

A decoration shape can be written as :
```
shape,fill_color[:stroke_color]
```

**Note**
  1. a leaf label can have multiple decoration shapes, but only one decoration dataset can be shown at a time
  1. leaf labels can have different numbers of colour shapes; see more examples bellow.


Here is an annotated example of the dataset:

![https://lh5.googleusercontent.com/-GXsxHTotgI8/U00He0sm2hI/AAAAAAAAAVI/-cAvYMR5l2A/w582-h318-no/Edit_EvolViewDatasetLeafDecoration_-_evolgenius_-_Genius_ways_to_perform_evolutionary_analyses_-_Google_Project_Hosting.png](https://lh5.googleusercontent.com/-GXsxHTotgI8/U00He0sm2hI/AAAAAAAAAVI/-cAvYMR5l2A/w582-h318-no/Edit_EvolViewDatasetLeafDecoration_-_evolgenius_-_Genius_ways_to_perform_evolutionary_analyses_-_Google_Project_Hosting.png)

### Supported colour shapes ###
  1. triangle
  1. circle
  1. rect
  1. star
  1. check

### more examples ###
<table border='1'>
<tr>
<th>Dataset</th>
<th>Plot</th>
</tr>
<tr>
<td>
<pre>!defaultstrokewidth	0.7<br>
A	star,red<br>
B	rect,red	check,green<br>
C	star,white:red	triangle,white:green<br>
D	circle,white:green</pre>
</td>

<td><img src='https://lh3.googleusercontent.com/-isE-He6nGBU/U00GDNhls9I/AAAAAAAAAUk/pbsCGCT5xzY/w182-h121-no/EvolView___my_projects_and_trees.png' /></td>
</tr>
</table>