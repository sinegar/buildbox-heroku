# Buildbox Heroku

A ready to go setup for running your Buildbox Agent on Heroku.

## What you need

1. A Buildbox Account
2. A new Buildbox Agent ready to setup, and it's access token
3. Your Buildbox API key

## Setup

Create a git repository locally

```bash
$ git init
```

Clone the `buildbox-heroku` repo into your local repo

```bash
$ git remote add origin https://github.com/buildboxhq/buildbox-heroku.git
$ git pull
```

Create an application on Heroku

```bash
$ heroku apps:create [name]
```

Setup you Buildbox Credentials on Heroku

```bash
$ heroku config:set BUILDBOX_AGENTS=[agent token] BUILDBOX_API_KEY=[your api key]
```

Create a PostgreSQL Database (optional)

```bash
$ heroku addons:add heroku-postgresql:dev
$ heroku config | grep HEROKU_POSTGRESQL # Look for the color that Heroku chose for the database
$ heroku pg:promote HEROKU_POSTGRESQL_RED_URL
```

Deploy the code to Heroku

```bash
$ git push heroku master
```

Scale up the Buildbox Agent process

```bash
$ heroku ps:scale buildbox=1
```

That's it! If you `heroku logs --tail` you should be able to see your Buildbox Agent connecting and looking for builds.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Copyright

Copyright (c) 2013 Keith Pitt. See LICENSE for details.
