# KRAL #

A social media crawling engine, built on Django. 

Aims to provide a framework for rapidly collect data from social networks
based on defined search criteria. Built to be a foundation for a wide 
range of social applications, to bring accountability to the way in which 
data is collected, and promote others to get involved to help us collect 
as much data as possible with the fewest resources.

## Current Features ##

  * Ability to harvest user information, and posts from Twitter and 
  * Ability to expand all short-urls into full real URLs.
  * Modular design. Easily add or disable "kraling" for different social networks.


## Configuration Options ##


### KRALRS_ENABLED ###

All kralrs are enabled by default. To only enable certian kralrs, list them in KRALRS_ENABLED as a list in settings.py

Example (Only Facebook and Twitter Enabled):

    KRALRS_ENABLED = ["Twitter", "Facebook"]    


### USER_AGENT ###

Use USER_AGENT to masqurade as another browser

Example (Masqurade as Firefox):

    USER_AGENT = "Mozilla/5.0 (X11; U; Linux x86_64; en-US; rv:1.7.6) Gecko/20050512 Firefox"



## Starting and Watching Kralrs ##


Start all kralrs listed in KRALRS_ENABLED in settings.py (or ALL kralrs if it is not defined):

    ./manage.py celeryd -B


Start all kralrs listed in KRALRS_ENABLED in settings.py (or ALL kralrs if it is not defined) and watch verbose output:

    ./manage.py celeryd -B --purge --verbosity=2 --loglevel=INFO


Start only the Facebook kralr:

     ./manage.py --kralrs="Facebook" celeryd  -B --purge --verbosity=2 --loglevel=INFO


Start only the Facebook and Twitter kralrs:

     ./manage.py --kralrs="Facebook,Twitter" celeryd  -B --purge --verbosity=2 --loglevel=INFO


Ncurses Interface to monitor the database live:

     ./manage.py kral-monitor


## Notes ##

Many more features coming soon as this project is under active development.

This is by no means production-ready code. Do not actually use it in
production unless you wish to be eaten by a grue.

Questions/Comments? Please check us out on IRC via irc://udderweb.com/#uw
