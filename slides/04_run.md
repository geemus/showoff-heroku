!SLIDE
# Heroku: run #

!SLIDE commandline incremental smaller
# Status #

    $ heroku ps
    Process       State               Command
    ------------  ------------------  ------------------------------
    web.1         created for 5m

    $ heroku ps:restart web.1
    Restarting web.1 process... done

!SLIDE commandline incremental smaller
# Beyond 'web.#' Processes #

    $ heroku run ls
    Running ls attached to terminal... up, run.1
    [...]

    $ heroku ps
    Process       State               Command
    ------------  ------------------  ------------------------------
    run.1         complete for 12s    ls
    web.1         created for 7m

!SLIDE commandline incremental smaller
# Introspection #

    $ heroku logs
    2011-12-12T22:35:59+00:00 heroku[run.1]: State changed from created to starting
    2011-12-12T22:35:59+00:00 app[run.1]: Awaiting client
    2011-12-12T22:35:59+00:00 app[run.1]: Starting process with command `ls`
    2011-12-12T22:35:59+00:00 heroku[run.1]: Process exited
    2011-12-12T22:36:01+00:00 heroku[run.1]: State changed from starting to complete

!SLIDE commandline incremental smaller
# Auto Magic #

    $ cat Procfile
    web:          bundle exec rails server -p $PORT
    worker:       bundle exec rake resque:work QUEUE=*

    $ heroku scale web=1 worker=1
    Scaling processes... done
