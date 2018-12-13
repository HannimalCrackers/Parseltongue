## TEI and Mapping James Joyce's *Portrait*

&nbsp;
&nbsp;

#### Introduction

Let’s start with something fun. This map shows young Stephen Dedalus as he thinks about and moves through Dublin.


&nbsp;
  {% include joycemap.html %}
&nbsp; 

This map was created from the Open Editions version of *A Portrait of the Artist as a Young Man*, created by Jonathan Reeve and Hans Walter Gaber. Open Editions are XML files that are tagged according to the conventions of the Text Encoding Initiative (TEI), a customizable markup convention designed to facilitate automated parsing of texts.

In this post I will briefly explore (1) TEI as a process of data creation, and (2) how TEI encoding facilitates some interpretations of place but not others.


#### TEI as data creation
Tagging a text with TEI is data creation at its most explicit, and data creation is never neutral. Data do not exist independently of a decision to classify them as such. By inserting tags into a text we are privileging the information enclosed in the tags. Our decisions, when deciding what will be data, make specific kinds of analysis easier and thereby reduce friction to certain ways of knowing.


#### TEI place tagging in Portrait
The Open Editions are designed to be community projects and they are works in progress. Many people have contributed to the tagging, including students in a course taught by Jonathan Reeve. Some of the tags currently in use in A Portrait of the Artist as a Young Man specify which character is speaking, what language they are speaking, or indicate songs. There are also tags for places and locations mentioned in the text. Tagging places and locations presents an interesting set of challenges and choices.

Latitude and longitude coordinates, for instance, were included as geo tags so that places mentioned in the text could be easily mapped, but adding geographic coordinates may also imply a specific – and potentially misleading – level of detail. They work best for precise, local locations described in the text, e.g., the Wicklow Hotel. But places have also been geo tagged that cover large areas, like Greece and the Irish Sea. This can be problematic, as no single set of coordinates truly represent such places.

Nonetheless, while the level of detail implied by geo tags can be misleading, they can still be used to create useful maps.
I was able to create the animated map at the beginning of this post showing Stephen Dedalus’s movements around Dublin from the existing geo tags. Such visualizations are engaging and can help bring a story to life. There is, however, plenty to find fault with, including that the base map is of present-day Dublin rather than Dublin as-contemporaneous with the story, and that settings in the story which do not have identifiable coordinates are excluded entirely from mapping.

Another of the many questions when tagging places and locations – what to tag? Proper nouns is the easiest approach. But what are we capturing and what are we losing when we count mentions of “Dublin” but not “the city,” even if clearly referencing Dublin? Or, if taking a broader approach, how should a referent be tagged when it is not entirely clear to what it refers, or when it seems clear to one community editor but unclear to another

Further, I wonder if facilitating interpretation through geo tagging named locations obscures a more intimate reading of place. There are currently no tags that mark Stephen’s time in kitchens or on porches, though they are mentioned 12 and 9 times respectively in the text. Likewise, no tags mark when Stephen is indoors vs outdoors.


#### A little more about the map

I created the map at the beginning of this post by downloading the TEI-tagged Open Editions XML file and running it through BeautifulSoup using Python. I pulled all of the geo tags into a CSV, then loaded them into Carto to build the map.

One advantage of hosting the Open Editions on GitHub is that people can create their own parallel versions with which to work. In my copy of the text I created an additional category to track whether the places with geo tags were Stephen’s current location, places he was remembering, or places he was imagining. A version of the animated map that reflects this categorization is below (orange is current location, yellow is memory, purple is imagined). 

&nbsp;
  {% include joycemapcolors.html %}
&nbsp; 


#### Closing thoughts

TEI tagging provides a quick road in to many interesting stories about a text. Equally interesting is searching for the stories tags elide. This can be a valuable two-part exercise for a class who has been given a TEI text to explore. Students may be asked to use the tags to analyze a text, but also provide a brief writeup of what the analysis can’t take into account by virtue of relying on tags alone. It’s good to cultivate mindfulness around the limitations inherent in the creation of data, especially with human creative works.

Before leaving off, a great aspect of the Open Editions is the opportunity for any community member to suggest new tags or flag any errors in tagging. There is much work to be done and many opportunities to improve or refine the data structure. It is also a great resource for those who wish to analyze outside of the TEI tagging structure. The full text is available and can be used for any sort of textual analysis research. I encourage anyone interested in Joyce and/or in the use of TEI in literature to contact Jonathan and get involved.

