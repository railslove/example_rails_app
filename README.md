# example_rails_app

This is a repo to document the current Railslove-way of setting up a Rails app.

You can use this as a goal definition for bringing older projects up-to-date.

And you can use the text below as a starting point for the README of your fresh Rails app:

----

# Prequisites

* `docker` [installation](https://docs.docker.com/install/)
* `docker-compose` [installation](https://docs.docker.com/compose/install/)
* `ruby` (version specified in `Gemfile`)
* `node` (version specified in `package.json`: `engines.node`)

# Package installation

* `bundle install`
* `yarn install`

# Starting the app

Everything you need to run the app should by default be included in the repository.  All necessary `ENV` vars should have sensible defaults in the `.env` file, which is checked in into the repository.

### (otional) 

`cp .env.local.example .env.local` 

This way you can simply start the app by running:

* `docker-compose up`
* `rails db:setup`
* (`rake production_data:download_and_import`)
* `rails server`

# Configuration options

Use Rails secrets for sensitive credentials (unless they need to be ENV vars).

For more information see: [Ruby on Rails Stack docs](https://paper.dropbox.com/doc/Ruby-on-Rails-Stack--AhoqRW~2JNzwT8eLnUD8TFOvAg-MWCJEp2LzHBXTTXO61rot).


