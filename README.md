

## TELL ME MORE ABOUT SINATRA AND MVC!!!

Okay, okay! Here are some resources on the Model-View-Controller structure and Sinatra - the framework that we'll be using to create our web applications.

<img src="http://www.tonymarston.net/php-mysql/model-view-controller-01.png">

###It's all about documentation, documentation, documentation

Check out the [Sinatra Documentation](http://www.sinatrarb.com/intro.html)

###Sinatra MVC File Structure

#### What does the File Structure Look Like?

The file structure below is an example of what you will normally see in a Sinatra application.

```bash
sinatra-mvc-file-structure
├── Gemfile
├── Gemfile.lock
├── README.md
├── Rakefile
├── app
│   ├── controllers
│   │   └── application_controller.rb
│   ├── models
│   │   └── sample_model.rb
│   └── views
│       └── layout.erb
├── config
│   └── environment.rb
├── config.ru
├── db
│   ├── migrate
│   ├── seeds.rb
│   └── test.sqlite
├── public
│   └── stylesheets
└── spec
    ├── controllers
    ├── features
    ├── models
    │   └── sample_model_spec.rb
    └── spec_helper.rb
```

#### config.ru

A `config.ru` file is necessary if you are using a deployment tool such as `shotgun` (see `Gemfile`). It specifies to our app handler what files should be run in order to initialize a new server instance of our Sinatra application.

#### `app` directory

The `app` directory contains three directories: `controllers`, `models`, and `views`. This corresponds to the MVC paradigm, which splits up the responsibilities into directories in which logic is limited to its own domain side. This is otherwise known as the `separation of concerns`.

Our `controllers` directory has a file called `application_controller.rb` which inherits from `Sinatra::Base`, and serves as the starting point from which all other controllers inherit. The controllers in this directory handle requests, and then provide the corresponding response from your application.

#### `config` directory

The `config` directory stores our `environment.rb` file. The logic for setting up our environment (and the corresponding database configurations for each environment) goes in here.

#### `db` directory

The `db` directory currently has three items: a `migrate` directory, `seeds.rb` file, and a `test.sqlite` file. The `migrate` directory holds all of our database migration files, which sets up the tables and their corresponding logic in the database. The `seeds.rb` file holds the model objects that we want to pre-load into our database. For example, when you set up a new database, and you want a user named John to be preloaded in your database, you would include this in your seed file: `User.create(:name => "John")`. Finally, the `test.sqlite` is the raw database file into which we both store model data into and query model data from.

#### `public` directory

The `public` directory holds our front-end assets. In the example above, it holds a `stylesheets` directory where all of our stylesheets are located. Javascript directories and any other front-end assets would be stored in `public` as well.


<p data-visibility='hidden'>View <a href='https://learn.co/lessons/hs-mvc-resources' title=hs-mvc-resources>TELL ME MORE ABOUT SINATRA AND MVC!!!</a> on Learn.co and start learning to code for free.</p>
