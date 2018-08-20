
# setting up hannimalcrackers.com


&nbsp;
&nbsp;


## 180819
&nbsp;
Sitting in JFK waiting to board a flight to Iceland. Continuing with [part II of the Flask Mega-Tutorial](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-ii-templates).

Switching examples to be about my pets keep the coding interesting to me.

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/180819_templateposts.png)



&nbsp;
&nbsp;


## 180818
&nbsp;
It is crazy humid and I keep smelling ketones.

On to [part II of the Flask Mega-Tutorial](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-ii-templates).

Got partway through.

&nbsp;
&nbsp;


## 180817: polite math bot test
&nbsp;

I don't think this will work. I just want to see what happens.

1. Created new virtual environment. I'm still using Anaconda for this though I don't need to. Of note: Anaconda installs pip 10, so that needs upgrading.


2. Upgrade pip. 


```
$ pip install --upgrade pip
```

3. install Flask
```
$ pip install flask
```

4. umm....  create a subfolder for the app, bring the python file for the polite math bot over, copy the wsgi and other files/structure from the successful Hello World. Let's see... I'll add the polite math bot's division code to the routes file. Create a .flaskenv file.

Voilà!

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/mathbotworks_180817.png)

Ultimately I want this to be interactive in the browser, but it runs in terminal and returns a thank you in the browser. Yay!

I still have to figure out [deployment](http://flask.pocoo.org/docs/1.0/deploying/). Maybe I should look into a hosted option, like Heroku or something.

&nbsp;
&nbsp;


## 180817: helloing the world
&nbsp;

Ok, what I discovered yesterday troubleshooting with [this site](file:///Users/hhouse/anaconda3/envs/HannimalCrackers-com/lib/python3.6/site-packages/mod_wsgi/docs/user-guides/checking-your-installation.html) is that mod_wsgi is not showing up as a module added to Apache when I call $ /usr/sbin/httpd -M

Is this because it's in a virtual environment? I don't know. Having tried and failed more troubleshooting, I now can't even get the page with the bottle to load. Deleting the virtual environment and creating a new one to start fresh.

----

Ok, new day, new env, new me. Following the [Flask installation instructions](http://flask.pocoo.org/docs/1.0/quickstart/) I now have a Hello World running.

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/helloworld180817.png)


I'm going to go through [this Flask Mega-Tutorial](https://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world). 

So far so good. Have a slightly more complex file structure successfully producing a Hello World. 

#### Also installed python-dotenv and successfully created a .flaskenv file so I don't have to set FLASK_APP environment variable every time I relaunch terminal. 

Tested by relaunching Terminal.

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/hellohello_180817.png)

I'm going to see if I can get a polite math bot python script to run.

&nbsp;
&nbsp;


## 180816
&nbsp;

WSGI is killing me.



&nbsp;
&nbsp;


## 180815: a.m.
&nbsp;

WSGI [can run in environments](https://modwsgi.readthedocs.io/en/develop/user-guides/virtual-environments.html). There are instructions to configure WSGI. Not sure, but I think this is code added to WSGI app file.

Giving this a try. Not sure if I'm including the right amount of detail in the paths.
```python
from myapp import app as application

WSGIDaemonProcess myapp

WSGIProcessGroup myapp
WSGIApplicationGroup %{GLOBAL}

WSGIScriptAlias /Users/hhouse/anaconda3/envs/hannimalcrackers-com/myapp/myapp.wsgi

<Directory /Users/hhouse/anaconda3/envs/hannimalcrackers-com>
    Require all granted
</Directory>
```
--<br>
No dice. Still getting a 502 error. Have to go to work. Try again later.

&nbsp;
&nbsp;


## 180814: curses and fake things
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

This is the error. Terminal reports it as a 502.

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/fail_180814.png)

Been spinning my wheels trying to figure this out. So frustrating. Maybe I shouldn't have installed wsgi in the environment? That's my only guess right now. I did just discover wsgi installed some [user guides](/Users/hhouse/anaconda3/envs/HannimalCrackers-com/lib/python3.6/site-packages/mod_wsgi/docs/_sources/user-guides/checking-your-installation.rst.txt) so checking those out tomorrow. Calling it a night. 


&nbsp;
&nbsp;

## 180813
&nbsp;


Set up Google Analytics and added the code to the index.html file to test it out. Reading my 1 visitor (myself). I'm going with Flask as a framework. Having less built in will help/force me to learn what the different components do. I conda installed Flask and set up a Hello World Flask file. It worked running locally. Then I realized I should be working in a virtual environment, so I set one up in Anaconda.

To deploy Flask I need a webserver. Will probably go with Apache, since I've heard of it before and, while I want to learn, I don't want to go down a deep rabbit hole at every single decision point. However, having skimmed the [deployment](http://flask.pocoo.org/docs/1.0/deploying/#deployment) instructions, I'm not clear on how this goes. I'll need to read the instructions, including pointing to my environment, more closely when I pick this back up.

In the meantime, I've updated my homepage index file to note the impending change.

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/helloworldflask.png)


&nbsp;
&nbsp;


## 180812
&nbsp;


I registered the domain www.hannimalcrackers.com 5 or 6 months ago through Squarespace and pointed it at that time to my Squarespace graphics portfolio site. I've since been learning Python (aka parseltongue) and want to build a website to host my Python projects. I'll be using the hannimalcrackers.com domain for this new site.

I set up a hosting package with inmotion hosting because CNET recommended them and ¯\\_(ツ)_/¯. I planned to transfer management of the hannimalcrackers.com domain over to inmotion as well, but I would have had to take my privacy off it and set that back up again, which sounded like a pain, so instead I just pointed the nameservers to inmotion.

I wrote a quick hello HTML to test that all is working. Success. I also created an animal cracker favicon by outlining a photo of an animal cracker in Photoshop. A [free generator](http://tools.dynamicdrive.com/favicon/) output the .ico file.

![screenshot](http://hannimalcrackers.github.io/parseltongue/img/helloworld.png)


&nbsp;

&nbsp;


< [There's no place like home](../index.md)
