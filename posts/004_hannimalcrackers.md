
# setting up hannimalcrackers.com

&nbsp;
&nbsp;

## "progress" 180814: curses and fake things
&nbsp;

Tonight I want to figure out how to install/use Apache and [mod_wsgi](https://pypi.org/project/mod_wsgi/) in the Anaconda environment I set up last night. <br>
<br>
Ok, word is Apache is already in Mac OSX. Digging around online, it looks like I'm going to need to pip install mod_wsgi, so activating my environment in Terminal and using pip to install there. I still feel so bold working in Terminal. Well, brash, really, since I'm not confident. Hmm, I just upgraded pip from v10 to v18 because I was prompted. May have only upgraded it within the environment? Not sure. Idk how any of this works. <br>
<br>
Tested the mod_wsgi installation with $ mod_wsgi-express start-server and checked my browser. Ha, looks like it worked.

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/mod_wsgi_works.png)

Is this pronouced 'wise guy', perhaps? <br>
<br>
This wsgi.py test seems to be failing but I'm not sure. My browser shows an error when I check it.  $ mod_wsgi-express start-server wsgi.py --port 8080 <br>
This is probably a problem, but I don't know what to do about it. [Tried another test](https://davidhamann.de/2017/08/05/running-flask-with-wsgi-on-macos/) and this is failing too. Argh.
<br>

Wait, why is my environment full of curses and fake things?
![screenshot](http://hannimalcrackers.github.io/parseltongue/img/fakeandcurses.png)

Been spinning my wheels trying to figure this out. So frustrating. Maybe I shouldn't have installed wsgi in the environment? That's my only guess right now. Calling it a night. 

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/fail_180814.png)


&nbsp;

&nbsp;

## progress 180813
&nbsp;


Set up Google Analytics and added the code to the index.html file to test it out. Reading my 1 visitor (myself). I'm going with Flask as a framework. Having less built in will help/force me to learn what the different components do. I conda installed Flask and set up a Hello World Flask file. It worked running locally. Then I realized I should be working in a virtual environment, so I set one up in Anaconda.

To deploy Flask I need a webserver. Will probably go with Apache, since I've heard of it before and, while I want to learn, I don't want to go down a deep rabbit hole at every single decision point. However, having skimmed the [deployment](http://flask.pocoo.org/docs/1.0/deploying/#deployment) instructions, I'm not clear on how this goes. I'll need to read the instructions, including pointing to my environment, more closely when I pick this back up.

In the meantime, I've updated my homepage index file to note the impending change.

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/helloworldflask.png)


&nbsp;
&nbsp;


## progress 180812
&nbsp;


I registered the domain www.hannimalcrackers.com 5 or 6 months ago through Squarespace and pointed it at that time to my Squarespace graphics portfolio site. I've since been learning Python (aka parseltongue) and want to build a website to host my Python projects. I'll be using the hannimalcrackers.com domain for this new site.

I set up a hosting package with inmotion hosting because CNET recommended them and ¯\\_(ツ)_/¯. I planned to transfer management of the hannimalcrackers.com domain over to inmotion as well, but I would have had to take my privacy off it and set that back up again, which sounded like a pain, so instead I just pointed the nameservers to inmotion.

I wrote a quick hello HTML to test that all is working. Success. I also created an animal cracker favicon by outlining a photo of an animal cracker in Photoshop. A [free generator](http://tools.dynamicdrive.com/favicon/) output the .ico file.

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/helloworld.png)


&nbsp;

&nbsp;


< [There's no place like home](../index.md)
