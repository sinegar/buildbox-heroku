# Buildbox Heroku

A ready to go setup for running your Buildbox Agent on Heroku

## Installation

Create a git repository locally

    $ git init

Clone the `buildbox-heroku` repo into your local repo

    $ git remote add origin git@github.com:buildboxhq/buildbox-heroku.git
    $ git pull

Create an application on Heroku

    $ heroku apps:create [name]

Setup you Buildbox Credentials on Heroku

    $ heroku config:set BUILDBOX_AGENTS=[agent token] BUILDBOX_API_KEY=[your api key]

Create a PostgreSQL Database (optional)

    $ heroku addons:add heroku-postgresql:dev

Deploy the code to Heroku

    $ git push heroku master

Scale up the Buildbox Agent process

    $ heroku ps:scale buildbox=1

That's it! If you `heroku logs --tail` you should be able to see your Buildbox Agent connecting and looking for builds.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Copyright

Copyright (c) 2013 Keith Pitt. See LICENSE for details.
