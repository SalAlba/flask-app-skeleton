###### [Flask src.](https://github.com/pallets/flask/tree/1.0.2/examples/tutorial)
######


# Run The Application

You can run your application using the flask command. From the terminal, tell Flask where to find your application, then run it in development mode.

Development mode shows an interactive debugger whenever a page raises an exception, and restarts the server whenever you make changes to the code. You can leave it running and just reload the browser page as you follow the tutorial.

For Linux and Mac:

``` bash
    $ export FLASK_APP=app
    $ export FLASK_ENV=development
    $ flask run
```


For Windows cmd, use set instead of export:

``` bash
    $ set FLASK_APP=app
    $ set FLASK_ENV=development
    $ flask run
```

For Windows PowerShell, use $env: instead of export:

``` bash
    $env:FLASK_APP = "app"
    $env:FLASK_ENV = "development"
    flask run
```

You’ll see output similar to this:

``` bash
* Serving Flask app "name-of-your-app"
* Environment: development
* Debug mode: on
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
* Restarting with stat
* Debugger is active!
* Debugger PIN: 855-212-761
```

Visit [http://127.0.0.1:5000](http://127.0.0.1:5000) or [http://127.0.0.1:5000/hello](http://127.0.0.1:5000/hello) in a browser and you should see the “Hello, World!” message. Congratulations, you’re now running your Flask web application!


# Initialize the Database File

Now that init-db has been registered with the app, it can be called using the flask command, similar to the run command from the previous page.

------------------
### Note:

If you’re still running the server from the previous section, you can either stop the server, or run this command in a new terminal. If you use a new terminal, remember to change to your project directory and activate the env as described in Activate the [environment](http://flask.pocoo.org/docs/1.0/installation/#install-activate-env). You’ll also need to set FLASK_APP and FLASK_ENV as shown on the previous section.

------------------

Run the init-db command:

``` bash 
    $ flask init-db
```
There will now be a flaskr.sqlite file in the instance folder in your project.