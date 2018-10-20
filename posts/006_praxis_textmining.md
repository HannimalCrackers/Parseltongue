# From allegation to cloture: text mining US Senators' formal statements on Kavanaugh

&nbsp;
&nbsp;

Text-Mining Assignment (Due Oct 9) Explore a text or set of texts with Voyant (easiest), Bookworm, MALLET, or another text-mining tool. Blog about your experiences.

For this project I examined Senators’ formal public statements on the Kavanaugh nomination in the wake of Dr. Christine Blasey Ford’s allegation that he attempted to rape her as a teenager. I edited this out initially, but including now that this is an attempt to do something productive with how sick I feel at how hostile American culture remains toward women, our sexuality, and our safety.

&nbsp;

### process


I built my corpus for analysis by visiting every single one of the 99* official (and incredibly banal) US Senator websites and searching the term "Kavanaugh" using the search function on the site. I reviewed the first 20 search results** on each website and harvested the first result(s) (up to three) which met my criteria. My criteria were that they be direct, formal press released statements about Kavanaugh issued on or after September 15, 2018 up until the time of my research, which began at 5pm EST on October 5th. Some Senators had few or no formal statements in that period. I did not include in my results any speeches, video, news articles or shows, or op-eds. I only included formal statements, including officially-issued press released comments. For instances in which statements included quoted text and text outside of the quote area, I included only the quote area. 

I have publicly posted all of my data and results.

My working list of Senators and their official websites is from [an XML file I downloaded](https://www.senate.gov/general/contact_information/senators_cfm.cfm) from the United States Senate website. 

I opened the XML file in Excel and removed information not relevant to my text mining project, such as each Senate member's office address. I kept each member's last name, first name, state represented, party affiliation, and official webpage URL. This is my master list, posted to Google Sheets [here](https://docs.google.com/spreadsheets/d/12Ru1n23UvRC4Dn5ZDsfuveKO-VihdlgiO_r8CfctTjg/edit?usp=sharing).

I created a second sheet for the statements. It contains the Senators' last name along with date, title and content of the statement. I did a search for quote marks and effectively removed most or all of them. This statement content data is available in a Google Sheet [here](https://docs.google.com/spreadsheets/d/1YBD0VfqaUXuzLL-wHYQzSNpdYurndFbl6qV7Mo2UZ30/edit?usp=sharing).

I joined the two sheets in Tableau (outer join to accomodate future work I may do with this), and used Tableau's filtering capabilities to get four plain text files containing the Democrat's statements, Republican statement, Independant statements, and a consolidation with all statements. The plan is to perform topic modeling on each and compare.

### in the mangle

Mallet wasn't too hard to install following [these instructions](https://programminghistorian.org/en/lessons/topic-modeling-and-mallet#mac-instructions). I input my consolidated Democrat, Republican, and Independant statements and had it output a joined mallet file with stopwords removed. Then I ran train-topics, and here I really don't know what I was doing other than closely following the instructions. It worked? It made the 3 files it was supposed to make – two text files and a compresed .gz file. I have no idea what to do with any of them. Honestly, this is over my head and the explanations on the Mallet site presuppose more familiarity than I have with topic modeling. [Here is a link](https://drive.google.com/open?id=1jy38flWRsvAMdbTnLXnUtHYRBFFrDQzw) to the inputs I fed Mallet and what it gave back to me.


### discussion

At this point I'm frustrated with Mallet and my ignorance thereof (and, in the spirit of showing obstacles along the way, I'm cranky because I'm operating without full use of my right arm which was injured a few days ago). I like my corpus and I'd like to know more about topic modeling, but I'd like the learning process to be at least somewhat guided by a person who knows what they're doing. The readings are not adequate as sole preparation or context for trying to execute.

Something I found interesting when I was collecting my data is that not all Senators issued formal press release statements on Kavenaugh during the period I examined. I was suprised by some who didn't. Kamala Harris, Elizabeth Warren and Kirsten Gillibrand issued no formal statements between September 15th and the date of writing (October 5th), whereas Lindsay Graham issued four. This is not to say that the former Senators were silent on the topic. Just that they did not choose to issue formal statements. Searching for "Kavanaugh" on Chuck Schumer's site returned no results at all. Thinking this was in error, I manually reviewed his press release section going back to September 15th. Indeed, Kavanaugh was not mentioned one single time in the title of any of the many press releases.

And here's where I need collaborators, perhaps a political scientist and/or public relations expert who could contextualize the role that formal statements play in politics and why do or don't different Senators issue them.

There were other interesting findings as well. The search functions on the websites visited were all over the yard. Many had terrible indexing, returning the same result over and over in the list. Cory Booker's website returned 2,080 results for "Kavanaugh". Dianne Feinstein's site returned 6. Ten Senators' websites either lacked a search function or the search returned zero results.

I will likely run the data I gathered through Voyant or perform a different analysis tomorrow. If so, I will update this post accordingly.


NOTES

*Jon Kyl, John McCain's replacement, does not yet have an official Senate website of his own. A quick Google search revealed no official press release statements in the first 20 results.

**Bob Corker, Cindy Hyde-Smith, and John Kennedy did not have a search function on their sites. The search function on Rand Paul's site was not functioning. Each has a news or media section of their site, and that is where I looked for press releases. Chuck Schumer and Tina Smith's sites' search functions returned zero results for "Kavanaugh". I reviewed titles of all press releases on their sites since September 15th and found no reference to Kavanaugh.



### update 10/7

I wonder if I should be feeding Mallet the statements individually, rather than in consolidated text files grouped by party affiliation. I also realized I wanted to have these individually, rather than as cells in a CSV, so that I can feed into Voyant and see the comparisons between statements. I don't know how to write macros in Excel, but this seemed like a great application for a Python script. I've been trying to learn Python so decided to write a script that would import a CSV and export parts of the individual records as individual text files.

I wrote some Python code and got it working (with an assist from Reddit when an extraneous variable was tripping me up, and suggestions on how I could improve a future iteration from Patrick Smyth). I've posted the individual statements here. The filenaming convention is as follows. Filenames start with "D", "R", or "I" to indicate which party the senator belongs to (Democrat/Republican/Independent), followed by the Senator's surname, and a number that kept multiple statementss from the same senator from overwriting each other.

I plan to try analyzing these individual statements tomorrow.



### update 10/8

I took the statements I broke out in Python and ran them through Voyant. I ran the 56 statements from Democrats separately from the 42 statements from Republicans. I did not analyze the 4 statements from Independents, 3 of which were from Bernie Sanders. 

Voyant seems to be a bit buggy. I added "Kavanaugh," and "judge" to Voyant's default stopword list, as "Judge Kavanaugh" appeared in every single result, but it took a couple of tries and ultimately only worked on the Cirrus tool. Voyant refused to acknowledge my stopword list on the other tools. I'd also attempted to supress "Kavanaugh's", but Voyant kept showing it, including on the Cirrus tool, despite my adding it to the stopwords list. "Fire" is on the default stoplist, and I think it shouldn't be. Voyant also would not honor font changes, though there was a dropdown menu to do so. 

test
<iframe style='width: 461px; height: 359px;' src='//voyant-tools.org/tool/CollocatesGraph/?stopList=keywords-7ac4b8a0f96e66da8c3a205908e270f9&query=court&query=ford&query=dr&mode=corpus&corpus=f4e058c47489477c95d984d188b85990'></iframe>


### text mining tools review

Voyant: buggy, unreliable, sort of fun but about as rigorous as a party game
Mallet: a machine may have learned something, but I didn't



NOTES TO SELF

Should I be using Open Office or some other less proprietary solution than Excel? Maybe, but I can be more productive with the tools I know and don't have the luxury of time for any unnecessary trial and error on this assignment. That is a topic for another post.

It's valuable to understand that race and gender are categories that aren't always experienced internally the same as they are externally perceived. Still, it's problematic to throw out the categories entirely, lest we should lose why it's unsettling that the major groups of power in America, the ones making decisions about women's and minorities' lives, tend to all look like this.  [photo of GOP leaders]


Hashtags:  the banality of evil