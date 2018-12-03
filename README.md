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


# Make the Project Installable

See the (official packaging guide)[https://packaging.python.org/tutorials/packaging-projects/] for another explanation of the files and options used.


# Install the Project
Use **pip** to install your project in the virtual environment.

``` bash
    $ pip install -e .
```
This tells pip to find **setup.py** in the current directory and install it in editable or development mode. Editable mode means that as you make changes to your local code, you’ll only need to re-install if you change the metadata about the project, such as its dependencies.


# Running the Tests

To run the tests, use the **pytest** command. It will find and run all the test functions you’ve written.

``` bash

pytest

========================= test session starts ==========================
platform linux -- Python 3.6.4, pytest-3.5.0, py-1.5.3, pluggy-0.6.0
rootdir: /home/user/Projects/flask-tutorial, inifile: setup.cfg
collected 23 items

tests/test_auth.py ........                                      [ 34%]
tests/test_blog.py ............                                  [ 86%]
tests/test_db.py ..                                              [ 95%]
tests/test_factory.py ..                                         [100%]

====================== 24 passed in 0.64 seconds =======================
```

If any tests fail, pytest will show the error that was raised. You can run **pytest -v** to get a list of each test function rather than dots.

To measure the code coverage of your tests, use the **coverage** command to run pytest instead of running it directly.


``` bash

coverage run -m pytest

```
You can either view a simple coverage report in the terminal:

``` bash
coverage report

Name                 Stmts   Miss Branch BrPart  Cover
------------------------------------------------------
flaskr/__init__.py      21      0      2      0   100%
flaskr/auth.py          54      0     22      0   100%
flaskr/blog.py          54      0     16      0   100%
flaskr/db.py            24      0      4      0   100%
------------------------------------------------------
TOTAL                  153      0     44      0   100%
```

An HTML report allows you to see which lines were covered in each file:


``` bash
coverage html
```

This generates files in the htmlcov directory. Open htmlcov/index.html in your browser to see the report.