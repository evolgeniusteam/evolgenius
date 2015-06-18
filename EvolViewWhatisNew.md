## What's new ##

#### coming soon (Dec 15, 2014) ####
  * add images to nodes / branches (??)
  * hide / show names of internal nodes

#### April 4, 2015 ####
  * bug fixes as always
  * added a new annotation type, heatmap:

![https://www.evernote.com/shard/s130/sh/44d70834-aeb4-4fb0-86cc-258eb06a6f0a/c9c06609fa5ab4562c3be3bacd8fbd1c/res/5b2444ff-a1c1-4845-a3d6-d4dca88bd0e3/skitch.png](https://www.evernote.com/shard/s130/sh/44d70834-aeb4-4fb0-86cc-258eb06a6f0a/c9c06609fa5ab4562c3be3bacd8fbd1c/res/5b2444ff-a1c1-4845-a3d6-d4dca88bd0e3/skitch.png)
> see here for [the documentation for heatmap](EvolViewDatasetHeatmap.md).

#### March 31, 2015 ####
  * bug fixes (there are always bugs somewhere ... )
  * added a new annotation type: dot plot; here is an example:
![https://www.evernote.com/shard/s130/sh/2243ad16-1f95-45ef-b35e-7cbf7e7e466f/bff76fb9b9eff51464723c49a8223b9e/res/af4566e9-4925-4037-ba7e-2bd9ec128f98/skitch.png](https://www.evernote.com/shard/s130/sh/2243ad16-1f95-45ef-b35e-7cbf7e7e466f/bff76fb9b9eff51464723c49a8223b9e/res/af4566e9-4925-4037-ba7e-2bd9ec128f98/skitch.png)
  * see here for [the documentation for dot plots](EvolViewDatasetDotplots.md)

#### March 24, 2015 ####
  * bug fixes
  * updated the pfam domain api
  * added four more styles for group labels; See [here for the documentation](https://code.google.com/p/evolgenius/wiki/EvolViewDatasetGroupLabels).
  * added two more example trees to the 'DEMOS' project to showcase the group labels

#### Jan 2, 2015 ####
  * fixed a bug in tree sharing caused by case-sensitive setting of MySQL at the server-end

#### Dec 15, 2014 ####
  * a major update has just been released, with a new feature that allows users to share trees to others to view, interact and even edit. See [here for the documentation](https://code.google.com/p/evolgenius/wiki/EvolViewSharing).
  * NOTE: this function is still under development; bugs are thus expected. Please send us feature requests, comments and suggestions!!

#### Dec 15, 2014 ####
  * added support for a new type of annotation: Group Labels; here is an example:
![https://www.evernote.com/shard/s130/sh/221de2a1-870c-4690-99f1-1b7cac0c2bef/7fabcb088a21d7ab19b6cf244c7dcdaf/res/b2040157-660f-4200-b657-d80c50ccb4a5/skitch.png](https://www.evernote.com/shard/s130/sh/221de2a1-870c-4690-99f1-1b7cac0c2bef/7fabcb088a21d7ab19b6cf244c7dcdaf/res/b2040157-660f-4200-b657-d80c50ccb4a5/skitch.png)

See [here for the documentation](https://code.google.com/p/evolgenius/wiki/EvolViewDatasetGroupLabels).

#### Oct 9, 2014 ####
  * bug fixes
#### Oct 1, 2014 ####
  * fixed a UI bug that the UI behaves differently between firefox and google chrome.

#### Sep 28, 2014 ####
  * added support for the display of data values in pie and bar charts; see trees 'yeast duplicates' and 'bars' in the "DEMOS" project
> here are how the resulting plot look like:
> for pie charts (see [here](EvolViewDatasetPieCharts#show_data_value.md) for details):
![https://lh4.googleusercontent.com/-ff51XU2Ttjw/VChwjWl5LAI/AAAAAAAAAXE/9nG_qbjTyec/w779-h443-no/EvolView__project_-_DEMOS__tree_-_yeast_duplications.png](https://lh4.googleusercontent.com/-ff51XU2Ttjw/VChwjWl5LAI/AAAAAAAAAXE/9nG_qbjTyec/w779-h443-no/EvolView__project_-_DEMOS__tree_-_yeast_duplications.png)

> for bar charts (see [here](EvolViewDatasetBars#show_data_value.md) for details):
![https://lh5.googleusercontent.com/-tXXgeVyDubU/VChwbl0XoGI/AAAAAAAAAW8/9qPDa9Irqw4/w282-h125-no/EvolView__project_-_DEMOS__tree_-_bars.png](https://lh5.googleusercontent.com/-tXXgeVyDubU/VChwbl0XoGI/AAAAAAAAAW8/9qPDa9Irqw4/w282-h125-no/EvolView__project_-_DEMOS__tree_-_bars.png)


#### Sep 23, 2014 ####
  * added a new button "show /hide lines linking leaf labels and datasets" to the "Basic" tab; mouse over this icon to see larger image for more details.

#### July 4, 2014 ####
  * bug fix

#### June 23, 2014 ####
  * added rotate subtree at internal nodes

#### June 20, 2014 ####
  * bug fix: fixed a bug that the tree panel doesn't show properly in Firefox

#### June 18, 2014 ####
  * added support for navigation (beta)
  * added a new modifier 'toroot' for branch colors; see [here](EvolViewDatasetBranchColor.md) for examples

#### April 2, 2014 ####
  * now Firefox is officially back!! Enjoy!!

#### March 27, 2014 ####
  * new features:
    1. add support for stroke colour and stroke width; see [here](EvolViewAboutStroke.md) for more details
    1. add a new dataset type : [Leaf label decorations](EvolViewDatasetLeafDecoration.md)

#### Sep 11, 2013 ####
  * fix a bug with trees that have bootstrap values but no branch lengths : ((a,b)0.88,(c,d)0.99);
  * new features:
    1. (beta) social login: now evolview supports OAuth 2.0, an open standard for authorization; users can login with existing accounts including Facebook, Gmail, Windows Live, Yahoo and many others. See here for more information about OAuth: http://en.wikipedia.org/wiki/OAuth
    1. now users can set the fonts of bootstrap or branch length values to italic and change their sizes; all changes will be saved on to the server

#### April 18, 2013 ####
  * fix a bug caused by tree like this '((a:1,b):3,(c:1,(d:1,e:3):1):2);'
  * new features:
    1. temporary users can save their trees, projects and datasets on our server up to 7 days and the keys for accessing the data are saved in browser cookies (clearing the browser cookies will lose the keys) (Note: each temporary use would have a unique ID, she / he can use it to retrieve their data by emailing it to the server administrator )
    1. when creating a new account, temporary uses can choose to move their data to the newly created account

#### May 22, 2012 ####
  * manuscript accepted for publication on NAR 2012 Web Server issue. Check it out on the publisher's website: http://nar.oxfordjournals.org/content/40/W1/W569

#### Build# 510; May 15, 2012 ####
  * add visualization for protein domains
  * add automatic annotation for protein domains using tree leaf label names to query against PFAM database
  * see here for more details: EvolViewProteinDomain

#### Build# 500; May 12, 2012 ####
  * fix a bug on parsing the bootstrap scores in newick format
  * fix some usability issues

#### Build# 450; Apr 23, 2012 ####
  * improvement on pie-chars: now user can specify whether to use the summation of a row as the area of a pie, or the radius
  * now each plotmode/ treemode has independent translateX, Y as well as pixal per width values; and all these values will be saved on our server if a user is logged in
  * fix a bug on parsing the bootstrap scores in PhyloXML format

#### Build# 412; Feb 14, 2012 ####
  * fix several bugs on submitting datasets to trees;
  * fix a bug on parsing "legend"-related information from datasets

#### Build# 400; Feb 2, 2012 ####
  * the last active tree will be loaded automatically when sign in; however, if the last active tree is in project "DEMOS", no tree will be loaded
  * better compatibility (import/ export) with the following formats: nexus, phyloXML; better support for internal branches from imported trees
  * new download popup panel

#### Build# 380; Jan 17, 2012 ####

  * zoom in and out at the mouse pointer
  * fix a bug at parsing trees in PhyloXML format
  * add statistics on users' visits per month (click the EvolView logo at the login page to view the statistics)
  * add more interactivity with the tree branches

#### Build# 200; milestone 1; Dec 28, 2012 ####
  * first version available online
  * manuscript submitted to NAR web server [issue 2012](https://code.google.com/p/evolgenius/issues/detail?id=2012)