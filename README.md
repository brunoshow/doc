# appointment app

The goal is to have a starter project of appointment apps.

**This app is just for a test! It is still being developed and it will change in the future.**

## Try it now!

```
git clone https://github.com/beeman/loopback-angular-admin.git my-project
cd my-project
heroku apps:create my-project
git push heroku master
```

## Features and implemented projects

- The automatic type-safe REST library for Xamarin and .NET [Refit paulbets](https://github.com/paulcbetts/refit)
- An addictive .NET IoC container [Autofac](http://autofac.org)
- Angular UI-Router

## TODO:

- Permissions on user actions (non-admins cannot access advanced functions)
- permissions on content items (non-admins can only edit own content, etc)
- Detect if API is online [HubSpot/offline](https://github.com/HubSpot/offline)?
- Map API roles to [Narzerus/angular-permission](https://github.com/Narzerus/angular-permission)
- Add tests
- Add Dockerfile
- Add Vagrantfile


[Tell me what we need more!](https://github.com/beeman/loopback-angular-admin/issues/new)

## Screenshots
#### Dashboard
![](screenshots/dashboard.png?raw=true)
#### Markdown Editor
![](screenshots/pages.png?raw=true)
#### SweetAlert
![](screenshots/sweetalert.png?raw=true)
#### File uploads
![](screenshots/files.png?raw=true)
#### Events
![](screenshots/events.png?raw=true)

## Installation

### Dependencies

Installation depends on `node`/`npm` with `grunt` and `bower` installed globally.

    $ npm install -g bower grunt-cli

### The one-liner install (please create an [issue](https://github.com/beeman/loopback-angular-admin/issues/new) if this one does not work!)

    git clone https://github.com/beeman/loopback-angular-admin.git && cd loopback-angular-admin && npm install && grunt build && grunt serve

### The steps above: 

### Checkout the project:

    git clone https://github.com/beeman/loopback-angular-admin.git

### Install the Node packages:

    npm install

### Run grunt build:

    grunt build
    
### Run grunt serve to start the API and frontend:

    grunt serve
    

## Running

The project is separated in a server and a client.

### Server

To run the server you issue the command:

    npm start

Or to run it with nodemon (needs `nodemon` installed globally). This will
automatically restart the server when you change its code:

    npm run dev

The command `grunt serve` explained below wil automatically start the API.

### Client

Rebuild the lb-services.js file with the correct `API_URL` for development.

    API_URL=http://0.0.0.0:3000/api grunt

To run the client you issue the command. This will also start the API.

    grunt serve

It will open the project in your default browser with livereload enabled.
This will take care of reloading the page when you change your code.

## Connect to a database

You can specify the URL to the MongoDB database you want to use with the `MONGODB_URL` environment variable.

    MONGODB_URL="mongodb://localhost:27017/loopback-angular-admin" npm start

Set `INITDB` to true if you want to load the initial dataset, which creates the admin user. The memory database (default) does this automatically.

    INITDB=true MONGODB_URL="mongodb://localhost:27017/loopback-angular-admin" npm start

This also works with the free hosted MongoDB instances at [compose.io](https://www.compose.io) and [mongolab.com](https://mongolab.com)!

## API Security

**WARNING: Most models don't have an ACL configured. This means that anyone with access to the API can edit most of it's content.**

To access models with access control enable you need an AccessToken. You can get an access token by logging in to the API.

To ease development you can create an AccessToken while starting the server by setting the DEV_ACCESS_TOKEN environment variable. 

    DEV_ACCESS_TOKEN=MySecretToken npm run dev

## Development

If you want to share your work through a Pull Request, be sure to make it a clean branch (one functionality per PR) and base it off master.

If you plan on making a big change or replace a core function with something else it is probably best to first open an issue to discuss it with me. This will enhance the chance of the eventual changes getting merged a lot :)

The API is built with [generator-loopback](https://www.npmjs.org/package/generator-loopback).

The GUI is built with [generator-angular](https://www.npmjs.org/package/generator-angular) but is no longer compatible due to refactoring the project into modules.

These should help you quickly add code to your project. Further details tailored to this project might follow in the future.


## Unit Testing using Karma/Jasmine

    $ node_modules/.bin/karma start client/test/karma.conf.js

    INFO [karma]: Karma v0.12.31 server started at http://localhost:8080/
    INFO [launcher]: Starting browser PhantomJS
    INFO [PhantomJS 1.9.8 (Linux)]: Connected on socket aLJmRuSNUH2rPfpWgS3l with id 89641972
    PhantomJS 1.9.8 (Linux): Executed 1 of 1 SUCCESS (0.007 secs / 0.029 secs)


### Useful commits

These commits might be useful when extending the functionality.

- [Add support for MongoDB databases](https://github.com/beeman/loopback-angular-admin/commit/6b884e601d535ed64b4ef4f6f07e0f55d357a5b6)
- [Add custom method to the API](https://github.com/beeman/loopback-angular-admin/commit/eedbd03f755ddf2234872886ee390ac4f6753c64)
- [Rename a model](https://github.com/beeman/loopback-angular-admin/commit/88254ce59af29818aec900514693e3fe6c94acea)

### WebSockets / socket.io

At this moment there is no integration for socket.io or websockets, nor will there be in the near future. Once LoopBack has integrated support for it we will leverage from that.

Having that said, it's certainly possible to integrate socket.io, check [this](https://github.com/beeman/loopback-angular-admin/pull/44) pull request by [@movibe](https://github.com/movibe).

# Related Projects

Here are some projects that are related to what this project does. Please send a PR or create an issue if you have any additions to this list.

- [BoLaMN/loopback-component-admin](https://github.com/BoLaMN/loopback-component-admin) 
- [johannesjo/generator-angular-auto-admin-loopback](https://github.com/johannesjo/generator-angular-auto-admin-loopback)

# Issues

If you have any problems please [contact me](https://github.com/beeman/loopback-angular-admin/issues/new).
