I prefer my original mapping praxis post [https://dhintro18.commons.gc.cuny.edu/2018/10/23/illustration-maps-and-stories/] , but it's a little lightweight and I've belatedly noticed the requirement on the syllabus that we use a mapping platform. So here is take 2.

I live in an area with a lot of film and television shooting activity. Our readings have me thinking about what it means for certain parts of the city to be shown often in mass media, while others may never appear at all. T

I created a dashboard of maps with the Film Permits dataset accessed through the NYC OpenData portal [https://data.cityofnewyork.us/City-Government/Film-Permits/tg4x-b46p] . The colored dots indicate the locations by zip code of shooting permits issued in the three-year period from 8/1/15 - 7/31/18 for commercials, documentaries, films, and television shows. Larger dots represent more activity.

These maps show greater total number and diversity in location for film and television permits. I'm interested in how mapping can be used to show absence, so the map that is most interesting to me on this dashboard is the one showing shooting permits for documentaries. Over the past three years the majority of permitted documentary shooting activity has been in Manhattan and Brooklyn, with only a few projects in the Bronx and Queens, and only one in Staten Island. Less information and data of this type are being created about the Bronx, Queens and Staten Island, which shapes how much presence they have both in current cultural awareness and how much will be available to people who wish to learn about these places in the future.

Learnings: 
1. The raw data included multiple zipcodes for some permits in a single cell. I broke them apart into separate columns in Excel, then wrote a Python script that used Pandas and the melt function (method?) to reshape this into long, skinny data that Tableau could use to map each zip code separately. It would be better if I could have done the entire thing in Python, but I was under a time constraint and doing the first part in Excel was faster for me.

2. I'd destructively pared the dataset down to cover only three years by deleting the other rows in Excel. I should have left the data intact to leave myself the option of adjusting the timeframe using Tableau filters. Shooting permit data went back to 2012 in the original dataset. I'd like to map all available documentary permitting data to get an expanded view of which parts of the city are the topic of formal archival(?) content creation.

Things I need to learn how to do that would improve this dashboard: (1) include scale reference for each map, as the scale for the dots is not the same between them, and (2) synchronize the area shown in the maps to be identical.

A potential critical error with this project: I'm not sure whether shooting permits are also issued for shooting on permanent stage sets. I've inquired with a friend who works in film and will update this post when I hear back.
