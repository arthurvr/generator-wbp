# Contributing

Go crazy with suggestions and requests, I'm listening.

I created this generator for myself and my purposes, which means that I'll be maintaining it regularly (until something better comes along). This also means that I will reject requests that are not really my style (sorry), but you can be sure that I'll consider them carefully.

I want to make this generator a collection of best practices and I will do my best to document here why I made certain choices.

## Browserify

I used to use [Bower] + [wiredep] (like we do in [generator-gulp-webapp]), but Browserify offers Node-like `require()`, which improves authoring experience and frees you of worrying about the source order. Also, it consumes npm packages, which we're using for development anyway, so that's one less package manager to worry about.

I'm open for convincing to move to an alternative, like [webpack], I just haven't tried it for real yet, because the learning curve seemed steeper.

## React

I chose React among other frameworks because it's simple, modern, and unobtrusive, which means that it can be combined with other frameworks. It worked great for me so far and is the only one for which I can say that I kinda-sorta mastered.

I made it optional because there is a good chance you'll want something else, and removing it manually each time isn't trivial.

## Sass

I'm aware that other CSS pre-processors exist, but Sass has the strongest community and is blazing fast, now that [libsass] is a thing.

## PostCSS

It's a CSS post-processor, meaning that it should ideally process more-or-less valid CSS. [Autoprefixer] is a great example of a PostCSS plugin, you can pretend like you're writing CSS for the perfect browser, while it takes care of all the prefixes.

Because I'm using [gulp-postcss] and not [gulp-autoprefixer] directly, you are free to add any number of [PostCSS plugins], just `require()` them and add them to the array of processors.

## SVG

I find SVG a much better choice for icons over icon fonts.

  * much smaller file size
  * more semantic
  * better accessibility
  * no spacing issues
  * multiple colors
  * opacity property
  * stroke property
  * etc.

The method that worked best for me is `<symbol>` + `<use>`, read more about it [here][svg-symbol].

## WebdriverIO

It's more advanced, has nicer API and is better-documented than [WebdriverJS].

I'm open for convincing to move to [wd]. It seems to have a very similar goal, but with a different API. I haven't tried it for real yet.

[bower]: http://bower.io/
[wiredep]: https://github.com/taptapship/wiredep
[generator-gulp-webapp]: https://github.com/yeoman/generator-gulp-webapp
[webpack]: http://webpack.github.io/
[libsass]: http://libsass.org/
[autoprefixer]: https://github.com/postcss/autoprefixer
[gulp-postcss]: https://github.com/postcss/gulp-postcss
[gulp-autoprefixer]: https://github.com/sindresorhus/gulp-autoprefixer
[postcss plugins]: https://github.com/postcss/postcss#plugins
[svg-symbol]: https://css-tricks.com/svg-symbol-good-choice-icons/
[webdriverjs]: https://code.google.com/p/selenium/wiki/WebDriverJs
[wd]: https://github.com/admc/wd
