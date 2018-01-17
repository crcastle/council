# Council [![Build Status](https://travis-ci.org/JeffreyWay/council.svg?branch=master)](https://travis-ci.org/JeffreyWay/council)

This is an open source forum that was built and maintained at Laracasts.com.

## Installation

### Step 1

> To run this project, you must have PHP 7 installed as a prerequisite.

Begin by cloning this repository to your machine, and installing all Composer & NPM dependencies.

```bash
git clone git@github.com:JeffreyWay/council.git
cd council && composer install && npm install
php artisan council:install
npm run dev
```

### Step 2

Next, boot up a server and visit your forum. If using a tool like Laravel Valet, of course the URL will default to `http://council.test`. 

1. Visit: `http://council.test/register` to register a new forum account.
2. Edit `config/council.php`, and add any email address that should be marked as an administrator.
3. Visit: `http://council.test/admin/channels` to seed your forum with one or more channels.

## Deploy

### Heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

This will deploy Council to Heroku for free including:

- Installing all Node.js and PHP dependencies
- Provisioning a free Heroku Redis database
- Provisioning a free JawsDB MySQL database
- Running `php artisan migrate --force` to setup the database schema

After deploying, you'll probably get an error if you try to view the public URL of your deployed app. You'll need to generate and set the `APP_KEY` environment variable to fix that. There are a few ways to do this:

1. If you have Artisan CLI and the Heroku CLI installed locally, you can run `heroku config:set APP_KEY=$(php artisan --no-ansi key:generate --show)`
1. If you have the Artisan CLI installed but not the Heroku CLI, you can run `php artisan key:generate --show` and paste the output into your app's [Settings tab on Dashboard](https://devcenter.heroku.com/articles/config-vars#setting-up-config-vars-for-a-deployed-application).
1. You can generate the key from Dashboard using the [Web Console](https://devcenter.heroku.com/articles/heroku-dashboard#web-console). Run `php artisan key:generate --show` and paste the output into your app's [Settings tab on Dashboard](https://devcenter.heroku.com/articles/config-vars#setting-up-config-vars-for-a-deployed-application).

Next, check out `.env.example` for other environment variables you may need to configure for email, Algolia, and Pusher.
