# Heroku p7zip Buildpack

A buildpack to install p7zip on a heroku dyno.

## Installation

Use heroku multi buildpack:

https://github.com/nolman/heroku-buildpack-multi

Note: you need a variant of the buildpack multi that allows you to chain exported variables from one buildpack to the next. For now my fork will work fine (using ./export from the buildpack), in the longer term there should be a standard way to chain buildpacks together.

To set this buildpack on heroku run the following:

```
heroku config:set BUILDPACK_URL="https://github.com/nolman/heroku-buildpack-multi"
```

Then add a .buildpacks file to your app:

```
https://github.com/opendoor-labs/heroku-p7zip-buildpack.git
https://github.com/heroku/heroku-buildpack-ruby.git#v119
```

You can replace the ruby buildpack with whatever your language of choice is.

## Known issues

Cannot set the AWS Bucket to download dependencies via an env var.

Pull requests welcome.
