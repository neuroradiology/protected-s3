# protected-s3

Simple application that allows you to display the content of your S3 to authorised users only.


## Installation

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

### Manual installation

* npm start

Don't forget to set environment variables:

* `NODE_ENV` to `production` (or your bucket will be open)
* `DOMAIN` to whatever domain you are on
* `USE_SSL` to `1` unless you have a very good reason not to (credentials might leak there)
* `ALLOWED_DOMAINS` to comma-separated list of domains you are accepting auth from
* `GOOGLE_CLIENT_ID` and `GOOGLE_CLIENT_SECRET` to whatever you requested from Google via 
  [their Developer Console](https://console.developers.google.com/). When prompted, your origins are the root of your 
  app (like `https://protected-s3.herokuapp.com/` and Authorized Redirect Uri is the former with 
  the `/auth/google/return` suffix (i.e. https://protected-s3.herokuapp.com/auth/google/return))
* `BUCKETS`, `ACCESS_KEY` and `SECRET_KEY` to the bucket you want to expose and Amazon Web Services S3 credentials.
* `USE_REDIS_SESSION` to `1` if you want to use Redis and have a persistent session (set `REDIS_URL` to the appropriate 
  value)
* `APP_PORT` if testing on localhost to whatever port you wish the app to run (don't forget to include the port in the 
  Authorized Redirect Uri when requesting Google app credentials) 

