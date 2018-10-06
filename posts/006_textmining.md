# From allegation to cloture: text mining US Senators' statements on Kavanaugh

&nbsp;
&nbsp;

Text-Mining Assignment (Due Oct 9) Explore a text or set of texts with Voyant (easiest), Bookworm, MALLET, or another text-mining tool. Blog about your experiences.

I'm trying to do something productive with how sick I feel at how hostile American culture remains toward women and how overwhelmingly prevalent is violence against us.

&nbsp;

### process

For this project I examined Senators' public statements on the Kavanaugh nomination in the wake of Dr. Christine Blasey Ford's allegations. 

My working list of Senators is from an XML file I downloaded from the United States Senate website. https://www.senate.gov/general/contact_information/senators_cfm.cfm

I opened the XML file in Excel and removed information not relevant to my text mining project, such as each Senate member's office address. I kept each member's last name, first name, state represented, party affiliation, and official webpage URL. 

My corpus for analysis came from searching the term "Kavanaugh" on each Senator's official website using their search function. I reviewed the first 20 search results on each website and harvested the first (up to three) which met my criteria. My criteria were that they be direct, formal press released statements about Kavanaugh issued on or after September 15, 2018. Some Senators had few or no formal statements in that period. I did not include speeches, video, news articles or shows, or op-eds in my results. I only included formal statements, including officially-issued press released comments. For instances in which statements included quoted text and text outside of the quote area, I included only the quote area. 

I created a second sheet for the statements. It contains the Senators' last name along with date, title and content of the statement.
All data has been posted online to Google Sheets [URL here]

I joined the two sheets in Tableau (outer join to accomodate future work I may do with this), and use Tableau's filtering capabilities to get plain text consolidations of the Democrat's statements, Republican statement, Independant statements, and a consolidation with all statements. The plan is to perform topic modeling on each and compare.





*Bob Corker, Cindy Hyde-Smith, and John Kennedy did not have a search function on their sites. The search function on Rand Paul's site was not functioning. Each has a news or media section of their site, and that is where I looked for press releases. Jon Kyl, John McCain's replacement, does not have an official Senate website of his own yet. A quick Google search revealed no official press release statements in the first 20 results. Chuck Schumer and Tina Smith's sites' search functions returned zero results for "Kavanaugh". I reviewed titles of all press releases on their sites since September 15th and found no reference to Kavanaugh.


Kamala Harris, Elizabeth Warren and Kirsten Gillibrand issued no formal statements between September 15th and the date of writing (October 5th), whereas Lindsay Graham issued four. Searching for "Kavanaugh" on Chuck Schumer's site returned no results at all.

A good collaboration for this project might have been with a political scientist or expert who could contextualize the role that formal statements play in politics.

Should I be using Open Office or some other less proprietary solution than Excel? Maybe. That is a topic for another post.

It's valuable to understand that race and gender are categories that aren't always experienced internally the same as they are externally perceived. Still, it's problematic to throw out the categories entirely, lest we should lose why it's unsettling that the major groups of power in America tend to all look like this.  [photo of GOP leaders]


Hashtags:  the banality of evil
