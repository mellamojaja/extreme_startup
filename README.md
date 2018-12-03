Welcome
=======
This is a for of [Extreme Startup project](https://github.com/rchatley/extreme_startup), by @Robert Chatley, modified to be used in a Code Challengue in my company. The main differences are:
# The addition of 3 new question types
# The hability to keep the score for each team even if they withdraw
# A corrected bug in the Fibonacci question type
# In each level, the main question types are the latest 4, but there is a small chance (30%) to consider also the older ones

Getting started
---------------
* Install Ruby 2.3.* and rubygems (the original project was designed to 1.9.6 but in order to be able to download gems you need 2.3 at least)
* (For Windows)
  * Install [Ruby DevKit](http://rubyinstaller.org/downloads/)
  * Extract to (e.g.) c:\devkit
  * cd c:\devkit
  * ruby dk.rb init
  * Edit the file config.yml (Add the locations where ruby is installed e.g. c:\Ruby193)
  * ruby dk.rb install

* Install dependencies:

````
cd ../<extreme startup dir>
gem install bundler
bundle install
````

* Start the game server

````
bundle exec ruby web_server.rb
````

Notes for facilitators
----------------------

* Run the server on your machine. It's a Sinatra app that by default runs on port 3000.
* Everyone needs a computer connected to the same network, so that they can communicate. Check that everyone can see the leaderboard page served by the webapp running on your machine. Depending on the situation, we have used a local/ad-hoc network and that is ok for the game.
* We have had trouble with things like firewalls, especially on some Windows laptops, so if there are problems, make sure you can ping clients from the server and vice versa.

* Warmup round: run the web server with the `WARMUP` environment variable set. This way, the server sends only 1 question ("what is your name"). To define the environment variable in Windows, use this: 


````
set WARMUP=1
````

And unset it like this:

````
set WARMUP=
```` 

* You may use the warmup round to make sure that everyone has something technologically working. @bodil has provided some [nice sample players in different languages](https://github.com/steria/extreme_startup_servers).

* Lenient mmode: Another environment variable you may setup is "LENIENT", that allows to avoid the susbtraction of points when you answer "" (empty string) to a any question. This is useful if you want the game to praise the good answers and not penalize the bad/unknown ones.

````
set LENIENT=1
````

* Real game: revert to using the full QuizMaster, and restart the server. This will clear any registered players, but that's ok.

* As the game progresses, you can introduce new question types by moving to the next round. Visit /controlpanel and press the "Advance round" button. Do this when you feel like some of the teams are making good progress in the current round. Typically we've found this to be about every 10 mins. But you can go faster/slower as you like. There are 7 rounds available.

* In case you want to 'stop the world' and reflect with the players
  during the game, you can use the "Pause Game" button in /controlpanel.

* Set a time limit so you know when to stop the game, declare the winner, and retrospect.
