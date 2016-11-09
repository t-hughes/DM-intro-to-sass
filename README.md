# DM-intro-to-sass
A simple introduction to SASS for DevMountain bootcamp students. SASS, LESS, and Stylus are the most popular CSS preprocessors. They allow for css file simplification by writing in a custom syntax, which is then processed into regular css. SASS is the most popular of them all. So, we'll introduce you to that. (Also see PostCSS--it's pretty sweet).


### Primary benefits of using a CSS preprocessor
* DRYer css
  - cleaner, more organized code (especially due to nesting)
  - reusable variables and pieces of code
* Saves you time when initially writing as well as maintaining
* Built-in calculations and logic (i.e. for loops, functions, conditionals, etc.)


### Getting started
You could use the CLI or a 3rd party gui (Instructions for both [here](http://sass-lang.com/install)), or even just play around on CodePen (enable SASS). But most likely, you'll want to incorporate css preprocessing into your project build process.

##### Webpack
`npm install --save-dev style-loader css-loader sass-loader`
```javascript
...
  loaders: [
    {
      test: /\.scss$/,
      loader: 'style!css!sass',
    }
  ],
...
```

### Sass files and syntax
Barrel, import
http://sass-lang.com/documentation/file.SASS_REFERENCE.html#syntax
variables
functions
mixins
nesting, &, BEM

### BEM
You should be using _some_ CSS naming methodology, for your own sanity, as well as that of your team. BEM is a popular one, and favors one-class-one-element structure, ensuring specificity is always in increments of one. (the [website](http://getbem.com/) is "getbem.com" but there is no download--it's just a recommended naming scheme).

##### tl:dr;
```css
.block {}
.block__element {}
.block__element--modifier {}
```
Schemes like BEM seem to have been made specifically with nesting in mind, because it makes things so fresh and so clean, clean:
```css
.card {
  font-size: 18px;
  &__title {
    font-size: 24px;
    margin-bottom: 16px;
  }
  &__body {
    color: gray;
    margin-bottom: 10px;
  }
}
```
```html
<div class="card">
  <h4 class="card__title">What up</h4>
  <p class="card__body">
    Here's all the text that no one will read in this handy little card element
  </p>
</div>
```
Isn't a single class like `.card__body` better than something like `div.card p`. Ew gross. Yes, yes it is. (Selectors like this have the potential to be excessively long and overly specific)
