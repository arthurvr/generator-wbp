# generator-wbp [![Travis CI](https://travis-ci.org/silvenon/generator-wbp.svg)](https://travis-ci.org/silvenon/generator-wbp)

> A [Yeoman] generator which provides a modern workflow for developing web apps and sites.

Heavily inspired by [generator-gulp-webapp], but far more opinionated. I want to make this generator as hardcore as it can be, starting a new project should be a breeze.

## Features

  * [gulp] for running tasks
  * [BrowserSync] for running the local server (it's loaded with features)
  * [browserify] for JS module bundling, with the following plugins:
    - [watchify] for watching and recompiling only modified scripts
    - [babelify] for transpiling scripts with [babel]
    - [browserify-shim] for fixing CommonJS-incompatible files
  * [React] for managing views, with the following plugins:
    - [React Router] for managing routes
    - [React Portal] for handling things like modals
  * [Fetch API polyfill] wrapped as a convenience helper
  * [FontFaceObserver] for [reducing FOIT][font-events] when using webfonts
  * [ESLint] for JS linting
  * [Sass] for CSS pre-processing (using [libsass])
  * [PostCSS] for CSS post-processing, with the following plugins:
    - [Autoprefixer] for adding vendor prefixes
    - easily include more [PostCSS plugins]
  * [gulp-sourcemaps] for CSS and JS sourcemaps
  * [Normalize.css] for normalizing styles across browsers
  * [imagemin] for image optimization
  * [SVG][svg-symbol] for icons (`<symbol>` + `<use>`) + [polyfill][svg4everybody] for IE
  * [selenium-standalone] for installing drivers and running the Selenium server
  * [Mocha] as the test framework
  * [WebdriverIO] as Node.js bindings for Selenium ([more info][integration-testing] about the setup)

See the current [roadmap].

## Getting Started

Install [yo] and this generator globally:

```sh
❯ npm install --global yo generator-wbp
```

Now create a new directory for your project:

```sh
❯ mkdir my-webapp
❯ cd my-webapp
```

and run the generator to start scaffolding:

```sh
❯ yo wbp
```

## Commands

There are some shortcut scripts in the [package.json] that you can run [using npm][scripts]. I'm not entirely sure that it's ok to use them that way, but you're not going to be publishing the generated "package" (which is why `private` is set to `true`), so we might as well abuse those.

Start the local server at http://localhost:9000 and watch files for changes:

```sh
❯ npm start
```

Run tests:

```sh
❯ npm test
```

Make a compressed production-ready build:

```sh
❯ npm run build
```

Preview the build, make sure nothing is broken:

```sh
❯ npm run preview
```

Deploy to S3 using [AWS CLI]:

```sh
❯ npm run deploy
```

This script needs to be adjusted according to your S3 data, or replace it with another script if you're deploying to somewhere else.

## Contributing

See the [contributing docs](CONTRIBUTING.md), interesting stuff.

## License

MIT © Matija Marohnić

[yeoman]: http://yeoman.io/
[generator-gulp-webapp]: https://github.com/yeoman/generator-gulp-webapp
[gulp]: http://gulpjs.com/
[browsersync]: http://www.browsersync.io/
[browserify]: http://browserify.org/
[watchify]: https://github.com/substack/watchify
[babelify]: https://github.com/babel/babelify
[babel]: https://babeljs.io/
[browserify-shim]: https://github.com/thlorenz/browserify-shim
[react]: https://facebook.github.io/react/
[react router]: http://rackt.github.io/react-router/
[react portal]: https://github.com/tajo/react-portal
[fetch api polyfill]: https://github.com/github/fetch
[fontfaceobserver]: https://github.com/bramstein/fontfaceobserver
[font-events]: http://www.filamentgroup.com/lab/font-events.html
[eslint]: http://eslint.org/
[sass]: http://sass-lang.com/
[libsass]: http://libsass.org/
[postcss]: https://github.com/postcss/postcss
[autoprefixer]: https://github.com/postcss/autoprefixer
[postcss plugins]: https://github.com/postcss/postcss#plugins
[gulp-sourcemaps]: https://github.com/floridoo/gulp-sourcemaps
[normalize.css]: http://necolas.github.io/normalize.css/
[imagemin]: https://github.com/imagemin/imagemin
[selenium-standalone]: https://github.com/vvo/selenium-standalone
[mocha]: http://mochajs.org/
[webdriverio]: http://webdriver.io/
[svg-symbol]: https://css-tricks.com/svg-symbol-good-choice-icons/
[svg4everybody]: https://github.com/jonathantneal/svg4everybody
[integration-testing]: http://twin.github.io/selenium-testing-workflow-with-webdriverio/
[roadmap]: https://github.com/silvenon/generator-wbp/labels/enhancement
[yo]: https://github.com/yeoman/yo
[package.json]: generators/app/templates/_package.json
[scripts]: https://docs.npmjs.com/files/package.json#scripts
[aws cli]: http://aws.amazon.com/cli/
