3/2/19

Searching for datasets for MALS 75500 project.

<br>

****TECHNOLOGY****

Using [Full Page Screen Capture](https://chrome.google.com/webstore/detail/full-page-screen-capture/fdpohaocaechififmbbbbbknoalclacl/related?hl=en) Chrome extension to create screen grabs of contents of page so I can compare downloaded contents to what was displayed later.

Using [Downloader for Instagram](https://chrome.google.com/webstore/detail/downloader-for-instagram/olkpikmlhoaojbbmmpejnimiglejmboe/related) Chrome Extension to download all instagram photos from accounts. Encountering something unexpected.

<br>

****TECH DISCREPANCY****

As of today, Alexandria Ocasio-Cortez's instagram says it has 382 posts, but the downloader identified 382, but then it downloaded 459 items. I tested with my own account and the number of items it says are posted exactly matched the number the downloader identifies. Meanwhile, the NYC Gov account says it has 374, the downloader said there were 371, but the downloader downloaded 387.

Andie suggested this may be due to multiple photos in posts, which makes sense except my account has some posts with multiple photos and my numbers match exactly. Need to resolve this. 


<br>

****DATASET****

Downloading all image posts from official Instagram accounts of top 10 cities in USA, as per wikipedia:
https://en.wikipedia.org/wiki/List_of_United_States_cities_by_population
New York, LA, Chicago, Houston, Phoenix, Philadelphia, San Antonio, San Diego, Dallas, San Jose

Only looking for top-level city instagram accounts, not accounts affiliated with a specific department or office.


New York
- official website: https://www1.nyc.gov
- official instagram: https://www.instagram.com/nycgov/
- instagram account linked from: https://www1.nyc.gov/connect/social-media.page
- instagram lists 374 posts, downloader downloaded 387

Los Angeles - NEED TO VERIFY
- ?? official website: https://www.lacity.org - why is this a .org instead of a .gov?
- ?? official instagram unclear, this one claims to be official: https://www.instagram.com/losangeles_city/?hl=en
- only a few instagram accounts specifically for Parks, DOT, etc mentioned on city site
- instagram lists 1,577 posts, downloader downloaded 1,577

Chicago - NONE
- official website: https://www.chicago.gov/city/en.html
- NO offical city instagram 

Houston
- official website: https://houstontx.gov
- official instagram: https://www.instagram.com/houston/
- instagram account linked from city site homepage
- instagram lists 169 posts, downloader downloaded 190

Phoenix
- official website: https://www.phoenix.gov
- official instagram: https://www.instagram.com/cityofphoenixaz/
- instagram account linked from city site homepage
- instagram lists 2,327 posts, downloader downloaded 2,560

Philadelphia
- official website: https://www.phila.gov
- official instagram: https://www.instagram.com/cityofphiladelphia/
- instagram account linked from city site homepage
- instagram lists 334 posts, downloader downloaded 400

San Antonio
- official website: https://www.sanantonio.gov
- official instagram: https://www.instagram.com/cosagov/
- instagram account linked from city site homepage
- instagram lists 413 posts, downloader downloaded 528

San Diego
- official website: https://www.sandiego.gov
- official instagram: https://www.instagram.com/thecityofsandiego/
- instagram account linked from city site homepage
- instagram lists 265 posts, downloader downloaded 394

Dallas - NEED TO VERIFY
- official website: https://dallascityhall.com/Pages/default.aspx  (this is a .com for some reason)
- official instagram: probably https://www.instagram.com/dallascityhall/?hl=en
- social media links on city site homepage do not include instagram, but some posts from dallascityhall insta account are in their social media archive
- instagram lists 157 posts, downloader downloaded 191

San Jose - NONE
- official website: http://www.sanjoseca.gov
- NO city level official instagram per http://www.sanjoseca.gov/index.aspx?NID=2425


<br>

****EVALUATION****

Human scale

Human perspective

Relatable to humans, like food or pets

Embodiment?


<br>

****THINGS DEPICTED****

Social events / sports / parades

Flowers

Empty streets, parks and plazas

Emptiness

Skylines

Public art

Seasonal / holiday (pumpkins, easter eggs, fireworks)

Typographic messages

Infrastructure

Groups or teams that won something

Drone / aerial shots

Landmark buildings

Weather events

Government proceedings or press events

Historic photos

<br>
-------------------
<br>

3/10/19

Was trying to make a project around photo framing and subject distance in public officials instagram accounts work, but that involves manually tagging and capturing likes / number of comments for each image on multiple accounts which is turning out too labor intensive for the timeframe I have to work with. So back to the city datasets.

Instagram has some weird coding for the images. Both exporting my own account using Instagram's downloader and using the downloader plug-in results in jpegs that were me trouble with the Google Vision API last week, though today I'm not getting an error.

Research argument: AI is an audience, and AI can only do distant reading. What are our big cities saying about themselves to AI?

Ideally I can run my images through multiple AIs. Not sure I'll have time though.

****Next steps****
1. select 5 images to test (pick from multiple city sets). Calling this mals75500_testset-a
2. convert images to PNG in Photoshop. Save As > PNG > Smallest file size. Calling this mals75500_testset-b
3. create cloud buckets for test sets A and B
4. develop python script to interact with Google Vision API and pull content lables only
5. test script on test set B and refine until works
6. once script working on test set B, try it on test set A to see if I can use Instagram images as downloaded or if they need to be resaved
7. confirm which city image sets are valid data for this project
8. upload each city into separate cloud bucket
9. run script on each bucket
10. write python script (possibly using pandas) to compile results into csv
11. explore and analyze results using Tableau visualizations
12. write up 

<br>

****Stages of data****
1. as-downloaded
2. unsure if needed: resaved, converted into png
3. 

<br>

3/16/19

****Setting up env and installing Google Cloud SDK****

First set up an env in anaconda, but didn't see a google cloud package so abandoned this route

Upgraded virtual env and pip using command line

Set up virutal env using command line (location: Projects/GoogleVision/VirtualEnv). Had to specify python 3 or I got a permisison denied error.

Installed Google Cloud SDK in the environment. Made new configuration called mals75500-cities. Also created new project called mals75500-cities. Using the same name might make this easier or might bite me later.

Everything is going unusually smoothly. *<<note from the future: that didn't last long*

I hope I set my configuration path correctly. Didn't get any acknowledgement message.

<br>

****Creating / uploading test images****

Set up storage buckets per my next steps above. Using bucket-level permissions. Did the PNG conversion for mals75500_testset-b and uploaded both image test sets to buckets.

<br>

****Test script with local image****

Created python script in my env using sample code on the Google Vision API Client Libraries page. Pointed it to a local test image. Ran the python script from the command line and it worked! My test image was the baby sugar glider I call "the thing." Results returned by the script were as follows.

Labels:

Hand

Bird

Pygmy slow loris

Finger

Beak

Nail

Perching bird

<br>

Now I need to modify the script to pull images from my test buckets online and return results as a csv or a json file. Also, the sample script only returned labels without the probability scores. Need to decide if I want the probability scores.

<br>

Not having an easy time trying to figure out how to get the label detection to run on all the images in a google cloud bucket. Made both buckets public.

Giving up on the buckets for now. May be easier to run the code bit that was working on a folder of images. Researching how to do that. My first foray into Bash!

<br>

****Bash Bash Bash****

```find /Users/hhouse/Desktop/DATASETS/MALS-75500/API-tests/mals75500_testset-b -name "*.png" -exec python /Users/hhouse/Projects/GoogleVision/VirtualEnv/env/test.py {} \;```

My bash party isn't panning out. I have the script and images in two separate places. The script needs to identify the image path, but it's picking up the script path (test3.py). Just going to chuck that script in the folder with the images for now as a workaround. Also I lost my authentication when I restarted Terminal.

I think the authentication command below needs to be run outside of virtual env at the root directory to take hold.

```export GOOGLE_APPLICATION_CREDENTIALS="/Users/hhouse/Projects/GoogleVision/GoogleVisionAPI/service-account-key/sacred-flash-207403-e10eed646ea0.json"```

<br>

3/17/19

My JSON dump isn't working (test6.py). Just going to try getting it all into a dictionary.

****Datasets****

Unclear if LA and Dallas are official accounts so leaving those out.

Cities I am analyzing are: New York City, Houston, Phoenix, Philadelphia, San Antonio, San Diego

<br>

****Scripting, continued****

I might hard code the city name into dict results generated by the script to save time. Definitely not ideal.

My dict is coming into the CSV with everything on one line. (test7.py, I think).

test8.py is writing each label onto a new line, but is only working on one image. Not writing labels for all the images. Maybe this is a "with open" thing? Moved "with open" out above the for loop and it works (test9.py)!

Now I need to shape these results. Would be tricky with GV returning different numbers of results for different pictures, but I already have the results stacking so I think that's good. Just need to get the dict keys moved out into column headers. Pandas time!

Hmmm, maybe the results should come in as a list instead of a dictionary. Testing this quickly (test9b.py). That's better. I need to get the brackets out. Pandas isn't recognizing the columns. I'm going to have to do this in Excel to save time.

Excel transformation is a success! Pandas is recognizing it as columns now. Though do I need Pandas now? The Excel CSV is probably in the shape I need. Going to run test9b.py (remaned to label-getter.py) on the full NYC set of images.

Running individual label-getter.py scripts for each city on the image sets. Takes a while. Excel is being a CHAMP. Phoenix has a large set. Excel just cheerily removed 105,942 quote marks in 1 or 2 seconds. "All done. We made 105942 replacements."


****Data journey****

1. Creation: download from Instagram using plug-in. Not "raw" because who knows what compressions it went through in user upload or by instagram. Also user may have cropped, used filters, or otherwise altered.
2. Python script (test9b.py, renaming label-getter.py) - to get labels from Google Vision. The path to the directory with images and the output filename are hard coded into the script. Change these for each city. Output of python script is the CSV.
3. Excel - remove brackets, remove quotes, replace comma-space with just comma, split column on comma. Manually add column with city name. Manually add header row with field labels [city, imagename, label, confidence, mid], save as CSV
4. Tableau - used to explore the data and make visualizations


<br>

****Choices made in data****

ignores mp4s


<br>

****Findings****

Did test where I shrank NYC image set images to 25% (took screen grab of exact settings used). This resulted in fewer nature features being identified. Full size versions had higher rankings for sky, trees, water, cloud, etc.

<br>

Left off with Phoenix. Need to remove mp4s from NYC, NYC_25pct, and Houston.



<br>

****190325****

Clean up script (remove JSON and maybe other imports)
