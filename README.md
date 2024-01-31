# heroku-buildpack-imagemagick

This is a Heroku Buildpack for vendoring the ImageMagick binaries into your project.

# Compatibility

This Buildpack is using ImageMagick v7.1.1-27 and compatible with `heroku-22` stack.

# Installation

### a. Via Heroku CLI

```
heroku buildpacks:add https://github.com/OneBacklog/heroku-buildpack-imagemagick --index 1 --app HEROKU_APP_NAME
```

"index 1" means that ImageMagick will be installed first.

### b. Via Heroku Dashboard

1. Go to your Heroku App's [Settings]
2. Scroll to [Buildpacks] and click [Add Buildpack]
3. Enter `https://github.com/OneBacklog/heroku-buildpack-imagemagick`
4. Adjust the order so this Buildpack is placed first

# Changing Version

1. Go to https://www.imagemagick.org/download/releases and find a version you want (*.tar.gz).
2. Edit the `bin/compile` file and change out the version number.
3. Clear cache as shown below and redeploy your app.

# Clear Cache

Since the installation is cached you might want to clean it out due to config changes.

1. `heroku plugins:install heroku-repo`
2. `heroku repo:purge_cache -app HEROKU_APP_NAME`
