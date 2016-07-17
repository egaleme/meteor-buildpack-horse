#Forked Meteor Buildpack Horse

[![Horse](https://i.imgur.com/YhIL9zM.jpg)](https://commons.wikimedia.org/wiki/File:Draw-Costa_Rican-2smallest.jpg)

This is a fork of heroku buildpack for Meteor v1+, without mongolab addon.

Create a sample app with 'meteor'

% meteor create --example todos

todos: created.

To run your new app:

   cd todos
   
   meteor
   
Put it in git.

% cd todos

% git init

Initialized empty Git repository in /tmp/a/todos/.git/

% git add .

% git commit -m "Sample todos app!"

Create your heroku app

% heroku create --buildpack https://github.com/egaleme/meteor-buildpack-horse.git

Or if your Heroku app already exists

% heroku buildpacks:set https://github.com/egaleme/meteor-buildpack-horse.git

Configure your plugins & settings

% heroku config:add MONGO_URL= your mlab database url here

% heroku config:add ROOT_URL= your heroku app url here

Add session affinity so your app will still work with more than one dyno

% heroku labs:enable http-session-affinity

Optional step, if you are using a settings.json file to configure your Meteor application

% heroku config:add METEOR_SETTINGS="$(cat settings.json)"

Deploy it

% git push heroku master

Enjoy!
