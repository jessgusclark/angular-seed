# angular-seed — the seed for AngularJS apps

[![Build Status](https://travis-ci.org/jessgusclark/angular-seed.svg)](https://travis-ci.org/jessgusclark/angular-seed)

This project is an application skeleton for a typical [AngularJS](http://angularjs.org/) web app.
You can use it to quickly bootstrap your angular webapp projects and dev environment for these
projects.

The seed contains a sample AngularJS application and is preconfigured to install the Angular
framework and a bunch of development and testing tools for instant web development gratification.

The seed app doesn't do much, just shows how to wire two controllers and views together.

## Forked Differences

There are a few small differences between this project and the official Angular seed project. One
configuration change so it can run better on my work machine and a few directory changes to help
organize the project better.

### Configuration Changes

- Added `directConnect: true,` to e2e-tets/protractor.config.js to run on Windows 8.

### Directory Changes

- Moved views to a /views folder for better orgnization
- Moved tests into /test folder

## Getting Started

After you have cloned this project install Node packages:

```
npm install
```

Then update the GIT origin path as to not overwrite this project:

```
git remote set-url origin git://new-path
```

### Run the Application

```
npm start
```

Now browse to the app at `http://localhost:8000/app/index.html`.


## Directory Layout

```
app/                    --> all of the source files for the application
  app.css               --> default stylesheet
  components/           --> all app specific modules
    version/              --> version related components
      version.js                 --> version module declaration and basic "version" value service
      version_test.js            --> "version" value service tests
      version-directive.js       --> custom directive that returns the current app version
      version-directive_test.js  --> version directive tests
      interpolate-filter.js      --> custom interpolation filter
      interpolate-filter_test.js --> interpolate filter tests
  views/
    home/                --> the home view template and logic
      home.html            --> the partial template
      home.js              --> the controller logic
    view1/                --> the view1 view template and logic
      view1.html            --> the partial template
      view1.js              --> the controller logic
    view2/                --> the view2 view template and logic
      view2.html            --> the partial template
      view2.js              --> the controller logic
  app.js                --> main application module
  index.html            --> app layout file (the main html template file of the app)
  index-async.html      --> just like index.html, but loads js files asynchronously
test
  karma.conf.js         --> config file for running unit tests with Karma
  e2e-tests/            --> end-to-end tests
    protractor-conf.js    --> Protractor config file
    scenarios.js          --> end-to-end scenarios to be run by Protractor
  unit
    home_test.js         --> tests of home controller
    view1_test.js         --> tests of view1 controller
    view2_test.js         --> tests of view2 controller    
```

## Testing

There are two kinds of tests in the angular-seed application: Unit tests and End to End tests.

### Running Unit Tests with Karma

```
npm test
```

### End to end testing with Protractor

```
npm start
```

In a second command prompt:

```
npm run protractor
```

If you have errors, first try updating webdriver.

```
npm run update-webdriver
```


### Running the App during Development

The angular-seed project comes preconfigured with a local development webserver.  It is a node.js
tool called [http-server][http-server].  You can start this webserver with `npm start` but you may choose to
install the tool globally:

```
sudo npm install -g http-server
```

Then you can start your own development web server to serve static files from a folder by
running:

```
http-server -a localhost -p 8000
```

Alternatively, you can choose to configure your own webserver, such as apache or nginx. Just
configure your server to serve the files under the `app/` directory.


### Running the App in Production

This really depends on how complex your app is and the overall infrastructure of your system, but
the general rule is that all you need in production are all the files under the `app/` directory.
Everything else should be omitted.

Angular apps are really just a bunch of static html, css and js files that just need to be hosted
somewhere they can be accessed by browsers.

If your Angular app is talking to the backend server via xhr or other means, you need to figure
out what is the best way to host the static files to comply with the same origin policy if
applicable. Usually this is done by hosting the files by the backend server or through
reverse-proxying the backend server(s) and webserver(s).


## Continuous Integration

### Travis CI

[Travis CI][travis] is a continuous integration service, which can monitor GitHub for new commits
to your repository and execute scripts such as building the app or running tests. The angular-seed
project contains a Travis configuration file, `.travis.yml`, which will cause Travis to run your
tests when you push to GitHub.

You will need to enable the integration between Travis and GitHub. See the Travis website for more
instruction on how to do this.

### CloudBees

CloudBees have provided a CI/deployment setup:

<a href="https://grandcentral.cloudbees.com/?CB_clickstart=https://raw.github.com/CloudBees-community/angular-js-clickstart/master/clickstart.json">
<img src="https://d3ko533tu1ozfq.cloudfront.net/clickstart/deployInstantly.png"/></a>

If you run this, you will get a cloned version of this repo to start working on in a private git repo,
along with a CI service (in Jenkins) hosted that will run unit and end to end tests in both Firefox and Chrome.


## Contact

For more information on AngularJS please check out http://angularjs.org/

[git]: http://git-scm.com/
[bower]: http://bower.io
[npm]: https://www.npmjs.org/
[node]: http://nodejs.org
[protractor]: https://github.com/angular/protractor
[jasmine]: http://jasmine.github.io
[karma]: http://karma-runner.github.io
[travis]: https://travis-ci.org/
[http-server]: https://github.com/nodeapps/http-server
