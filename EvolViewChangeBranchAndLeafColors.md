## change the branch and leaf colors of the tree ##
in the following we'll add several datasets to change the appearances of the tree.

Let's use the same tree again:
```
(chicken,((mouse,rat),(chimp,human)));
```

  * First of all add a dataset named "branch colors" to change the colors of the branches by clicking the "branch colors" icon on the "Annotation upload" tab:
> > <pre>
## lines start with # are annotations; you can put an annotation line<br>
##   anywhere in this dataset, provided that the # is the first character<br>
##   of the line<br>
## let the dataset begin: all fields of a line are seperated by 'tab'<br>
## first all, color all branches with 'grey'<br>
human,chicken	grey	ad<br>
## and then highlight the branches connecting human and chimp<br>
human,chimp	red	ad<br>
</pre>


|before applying the dataset|https://www.evernote.com/shard/s130/sh/5985b49b-7f2b-4eb9-b1ad-3afbbced36fb/0741ed72df13ce85414560ec32b52518|
|:--------------------------|:-----------------------------------------------------------------------------------------------------------|
|after                      |![https://www.evernote.com/shard/s130/sh/07f6ca6d-ec5a-4222-8423-107080345b7a/0cb1ef05cf50a0e38d300cf258989fd7/res/65fc691c-790d-477c-a67f-5b1d8dee4548/skitch.png](https://www.evernote.com/shard/s130/sh/07f6ca6d-ec5a-4222-8423-107080345b7a/0cb1ef05cf50a0e38d300cf258989fd7/res/65fc691c-790d-477c-a67f-5b1d8dee4548/skitch.png)|

  * then add another dataset to change colors of the tree leaves to match the colors of their corresponding branches by clicking the "tree leaf colors" icon on the "Annotation upload" tab:
> > ![https://www.evernote.com/shard/s130/sh/4c467292-8e44-4979-b37f-6ea0604289b2/3455f79768e9a981df79da482e7d6d87/res/20792906-d990-417e-8ddb-c6eafd5d6beb/skitch.png](https://www.evernote.com/shard/s130/sh/4c467292-8e44-4979-b37f-6ea0604289b2/3455f79768e9a981df79da482e7d6d87/res/20792906-d990-417e-8ddb-c6eafd5d6beb/skitch.png)
> > <pre>
## let the dataset begin<br>
##   each line of the 'data part' consists three fields sparated by a 'tab' character<br>
##   the first field specifies the location on the tree; for example 'human' indicates<br>
##     the leaf node representing 'human' or the branch connecting to this leaf node,<br>
##     while 'human,mouse' indicates the internal node representing the<br>
##     last common ancester (LCA) of human and mouse<br>
##   the second field specifies the color to be applied to the corresponding nodes / branches<br>
##   the third field is optional; it can be one the following 'key-words':<br>
##     ad: the color will be applied to all decendents of the node specified by the first field<br>
##     prefix: the color will be applied to all leaf nodes (or connecting branches) whose names<br>
##       start with the string in the first field<br>
##     suffix: the color will be applied to all leaf nodes (or connecting branches) whose names<br>
##       end with the string in the first field<br>
##     anywhere: the color will be applied to all leaf nodes (or connecting branches) whose names<br>
##       contain the string in the first field<br>
## first all, color all leaves to 'grey'<br>
human,chicken	grey	ad<br>
## then, highlight human and chimp with 'red'<br>
human,chimp	red	ad<br>
</pre>

|after applying the dataset|![https://www.evernote.com/shard/s130/sh/ce9c33ea-5a21-4634-b02a-d5a6248dbbfe/086b7a098ac766d8e7d2dacb9b5f6ebd/res/c2accd88-4b7c-4eb0-a71d-85cda77fdb36/skitch.png](https://www.evernote.com/shard/s130/sh/ce9c33ea-5a21-4634-b02a-d5a6248dbbfe/086b7a098ac766d8e7d2dacb9b5f6ebd/res/c2accd88-4b7c-4eb0-a71d-85cda77fdb36/skitch.png)|
|:-------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|