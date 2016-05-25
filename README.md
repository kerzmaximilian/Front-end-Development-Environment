# Front-end-Development-Environment
The environment is designed for time efficient Angular2 app development, using TypeScript, Jade and Sass.

## Quickstart

1. Pull repository and `cd` into it
2. Install npm dependency with: `$ npm install`
3. Initiate compilers and file watcher with: `$ gulp`
4. `cd` into app directory and start dev-server with: `$ lite-server`

NOTE: Make sure to install lite-server globally (`$ npm install -g lite-server`) before running it.


## Directory structure of development environment

    |── README.md
    |── app
    |    ├── app
    │   │   ├── app.component.js
    │   │   └── boot.js
    │   ├── css
    │   │   └── main.css
    │   ├── imgs
    │   ├── index.html
    │   └── views
    │       └── app.component.html
    ├── assets
    │   └── images
    ├── dev
    │   ├── jade
    │   │   ├── index.jade
    │   │   └── partials
    │   ├── sass
    │   │   ├── main.sass
    │   │   └── partials
    │   └── typescript
    │       ├── app.component.js
    │       ├── app.component.ts
    │       ├── boot.js
    │       └── boot.ts
    ├── gulpfile.js
    ├── package.json
    └── tsconfig.json

### Root Directory
The root directory contains the gulp file which watches any file changes in the `dev` directory, runs the appropriate compiler and writes the output file within the `app` directory.

### Dev Directory
All development should be done within this directory.
- All Angular2 components are stored in the `typescript` directory and should be named according to Angular2's convention.
- All html is specified in Jade syntax within the `jade` directory. In order to avoid cluttered typescript components, all html should be broken out in a separate `.jade` file and added to the `./jade/partials` directory. Gulp will take care of the rest.
- All css should be written in syntax friendly SASS. If you'd like to have component or topic specific `.sass` files, add them to the `./sass/partials` directory and import each file in the `./sass/main.sass` file. Gulp will take care of the rest.

### Assets Directory
All your assets should be added to the assets directory and imported in your typescript components or `.jade` files.

### App Directory
**DO NOT CHANGE ANY FILE WITHIN THIS DIRECTORY.** Gulp will compile your typescript components, jade and sass files and write them to the appropriate location within the `app` directory. Any changes that you'll make within this directory will be overwritten.

## Deployment

Once compiled, the `app` directory contains your entire Angular2 application. Copy it to your server, attach an Nginx or Apache Server and have it served as static files. You are done!
