# example_rails_app

This is a repo to document the current Railslove-way of setting up a Rails app.

You can e.g. use this repo as a reference for aligning older projects to the current conventions.

And you can use the text below as a starting point for the README of your fresh Rails app:

----

# Prerequisites

* `docker` [installation instructions](https://docs.docker.com/install/)
* `docker-compose` [installation instructions](https://docs.docker.com/compose/install/)
* `ruby` (version specified in `Gemfile`)
* `node` (version specified in `package.json`: `"engines.node"`)

# Package installation

* `bundle install`
* `yarn install`

# Starting the app

Everything you need to run the app should by default be included in the repository.  All necessary `ENV` vars should have sensible defaults in the `.env` file, which is checked in into the repository.

This way you can simply start the app by running:

* `docker-compose up`
* `rails db:setup`
* (`rake production_data:download_and_import`)
* `rails server`
* `bin/webpack-dev-server` (for hot reloading)

For some additional configuration options (e.g. sensible ENV vars, special local debugging cases) copy the following file:

`cp .env.local.development.example .env.local.development` 

# Configuration options

Use Rails secrets for sensitive credentials! If they **need** to be ENV vars, use the `.env.*.local` files to store these sensitive ENV vars.  Make sure that you add new ENV vars to both your local gitignored file (`.env.development.local`) **and** the checked in example file (`.env.development.local.example`). Adding an explanatory comment is also nice.

For more detailed information see: [Ruby on Rails Stack docs](https://paper.dropbox.com/doc/Ruby-on-Rails-Stack--AhoqRW~2JNzwT8eLnUD8TFOvAg-MWCJEp2LzHBXTTXO61rot).

# Exception tracking

We use [Sentry](https://sentry.io/) to track all exceptions that happen in production(/staging).

You can find the Sentry project here: https://sentry.io/organizations/railslove/issues/xxxxx

If you need to enable exception tracking in development (e.g. to adjust the Sentry integration), just uncomment/set the `SENTRY_DSN` ENV var in `.env.local.development`.
