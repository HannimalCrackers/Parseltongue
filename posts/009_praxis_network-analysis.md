This praxis project visualizes a network analysis of the bibliographies from the September 4th required readings in our [class syllabus](https://dhintro18.commons.gc.cuny.edu/syllabus/) plus the recommended "Digital Humanities" piece by Professor Gold.

I copy/pasted author names from the bibliographies of each reading into a spreadsheet. Data cleaning (and a potential point for the introduction of error) consisted of manually editing names as needed to make all follow the same format (last name, first initial). For items with summarized "et al" authorship, I looked up and included all author names.

I performed the network analysis in Cytoscape, aided by Miram Posner's clear and helpful tutorial [https://github.com/miriamposner/cytoscape_tutorials]. Visualizing helped me identify and fix errors in the data, such as an extra space causing two otherwise identical names to display separately.

The default Circular Layout option rendered an attractive graph with the nodes arranged around a perfect circle, however the labels overlapped and many were completely illegible. To fix the overlapping I individually adjusted the placement of the nodes, dragging alternating nodes either toward or away from the center to create room for each label to appear in its own space.


**Discussion**

This graph is not directional, but it would be interesting to create a second graph showing directionality by color coding the edges for in-degree vs. out-degree centrality.

We can see clearly that L. Spiro and S. Hockey had the largest bibliographies.

Loops at a node indicate the author citing themselves. Multiple lines connecting the same two nodes indicate multiple citations of pieces by the same author.

It is easy to see that all of the readings were connected in some way, with the exception of an isolated two-node constellation in the lower left of my graph. This constellation represents "The Humane Digital" by T. Burke, which had only one item (which was by J. Scott) in its bibliography. Neither T. Burke nor J. Scott authored nor were cited in any of the other readings, so they have no connections to the larger graph.

**A finding about names**
Any name changes, such as due to a change in marital status, will appear as two different people. This predominantly affects women and, without a corrective in place, could make them appear less central in graphed networks.

There are instances where people may have published with different sets of initials. In the bibliography to Hockey's 'The History of Humanities Computing,' an article by 'Wisbey, R.' is listed just above a collection edited by 'Wisbey, R. A.' These may be the same person but it cannot be determined with certainty from the bibliography data alone. Likewise, 'Robinson, P.' and 'Robinson, P. M. W.' are separately listed authors for works about Chaucer. These are likely the same person, but without further research I cannot be 100% certain. I chose to not manually intervene and so these entries remain separate. It is useful to be aware that changes in how one lists oneself in authorship may affect the how an algorithm understands a network.


**Potential problems with my visualization**
Doesn't distinguish between authors and editors
Had to split apart collaborative works into individual authors
Doesn't include works that had no author or editor listed





