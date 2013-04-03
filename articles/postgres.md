This guide walks through how you can setup a Heroku Postgres database
on your Action.IO box.

### Create a Database on Heroku Postgres

In: [Heroku Postgres](https://postgres.heroku.com)

![Heroku Postgres Homepage](https://raw.github.com/action-io/action-assets/master/support/screenshots/postgres/hpgres.png)

Go ahead and sign into Heroku Postgres. Once in the dashboard, you'll
see a list of any databases you've already created. Click the "Create
Database" button on the top-right of the screen.
You'll see a bunch of professional plans appear below. You can ignore
these until you've deployed your new world-changing application to
production and you have millions of customers and can afford them.

Heroku knows we need something lightweight to get our feet wet, so for
now we'll just pick the "Dev Plan (free)" option.

![Dev Plan Button](https://raw.github.com/action-io/action-assets/master/support/screenshots/postgres/dev-plan.png)

You'll see your new database at the top of your list of databases (or
just one if you just created an account). Heroku will create a zen name
for you, the one we created happens to have the name "salty-water-676".

![Create Database](https://raw.github.com/action-io/action-assets/master/support/screenshots/postgres/create-database.png)

For clarity lets rename the database so we know it's a development
database. Click the database you just created to navigate to the
database dashboard.
Click the database title and a modal will appear where you can change
the name of your database. Rename it something relevant to your
application, for e.g. if you were to make a to-do app, you can rename it
to "todo-app-dev".

![Rename Database](https://raw.github.com/action-io/action-assets/master/support/screenshots/postgres/database-rename.png)

### Heroku Postgres Connection Settings

In the *Heroku Postgres* website, click your database name
(todo-app-dev) to get to the database dashboard. You will see your
database connection settings listed, including "Host", "Database",
"User", "Port", "Password" (you will need to click 'Show' to reveal your
password).

![Heroku Settings](https://raw.github.com/action-io/action-assets/master/support/screenshots/postgres/heroku-settings.png)

Grab each of the values and assign them to environment variables in your
"~/.bashrc" file on your Action.IO box. This will ensure that every time you log into your Action.IO box, your
database credentials will be available as environment variables to use
in any of your apps. It is good practice to namespace your environment
variables with the environment that you want to use your database in
(development or test), like so:

![Env Variables](https://raw.github.com/action-io/action-assets/master/support/screenshots/postgres/env-variables.png)

If you want the environment variables to be loaded immediately, run:
    source ~/.bashrc

You can verify that your Postgres credentials are loaded correctly by
running:
    echo $TODO_APP_DEV_HOST

This should return "ec2-107-22-164-225.compute-1.amazonaws.com"

#### Rails/Ruby

You can now access your database in your Rails application by doing the
following:

    ENV['TODO_APP_DEV_HOST']
    ENV['TODO_APP_DEV_PORT']
    ENV['TODO_APP_DEV_USER']
    ENV['TODO_APP_DEV_PASSWORD']
    ENV['TODO_APP_DEV_DATABASE']

(Please note, you'll probably need to install the
[pg](http://rubygems.org/gems/pg) Rubygem 
before you use Postgres in a Rails app, using the following command:

    gem install pg

Here's an example of database.yml file used in Rails which uses the
environment variables to connect to the Heroku Postgres database you
created.

![Rails Postgres Settings](https://raw.github.com/action-io/action-assets/master/support/screenshots/postgres/database-ruby.png)

A more detailed tutorial is present on the [Action.IO
blog](http://blog.action.io/2013/02/11/postgres-action-io-3.html)

#### Node.JS

In Node.JS, you can access each of the environment variables by using:

    process.env.TODO_APP_DEV_HOST
    process.env.TODO_APP_DEV_PORT
    process.env.TODO_APP_DEV_USER
    process.env.TODO_APP_DEV_PASSWORD
    process.env.TODO_APP_DEV_DATABASE

(Please note, you'll probably need to install the
[pg](https://npmjs.org/package/pg) NPM 
before you use Postgres in a Node.JS app, using the following command:

    npm install -g pg

Here's an example nodejs code to connect to Heroku Postgres using the
environment variables we have set up.

![Postgres Settings](https://raw.github.com/action-io/action-assets/master/support/screenshots/postgres/database-nodejs.png)

#### Django/Python

In Python, you can access each of the environment variables by using:

    os.environ['TODO_APP_DEV_HOST']
    os.environ['TODO_APP_DEV_PORT']
    os.environ['TODO_APP_DEV_USER']
    os.environ['TODO_APP_DEV_PASSWORD']
    os.environ['TODO_APP_DEV_DATABASE']

(Please note, you'll probably need to install the
[psycopg2](http://initd.org/psycopg/) module
before you use Postgres in a Django app, using the following command:

    pip install --user psycopg2

Here's an example of a settings.py file which initializes the Heroku
Postgres credentials for use within a Django app.

![Postgres Settings](https://raw.github.com/action-io/action-assets/master/support/screenshots/postgres/database-python.png)

