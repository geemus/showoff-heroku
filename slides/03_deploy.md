!SLIDE
# Heroku: deploy #

!SLIDE commandline incremental smaller
# Deploy Zero #

    $ heroku apps:create sushi --stack=cedar
    Creating showoff-heroku... done, stack is cedar
    Created sushi.herokuapp.com | git@heroku.com:sushi.git
    Git remote heroku added

    $ git push heroku master
    -----> Heroku receiving push
    -----> Rails app detected
    -----> Compiled slug size is 8.0MB
    -----> Launching... done, v1
    http://sushi.herokuapp.com deployed to Heroku

!SLIDE bullets incremental smaller
# -----> What? #

* Heroku receiving push
* Rails app detected
* Compiled slug size is 8.0MB
* Launching... done, v1

