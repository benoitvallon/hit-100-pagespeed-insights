## Hit the 100 score on PageSpeed Insights

The goal of this project is to reach the 100 score on PageSpeed Insights. The project is based on the React Starter Kit (https://github.com/kriasoft/react-starter-kit)

## How to Build

```shell
$ npm run build                 # or, `npm run build -- release`
```

By default, it builds in a *debug* mode. If you need to build in a release
mode, just add `-- release` flag. This will optimize the output bundle for
production deployment.

## How to Run

```shell
$ npm start                     # or, `npm start -- release`
```

This will start a lightweight development server with "live reload" and
synchronized browsing across multiple devices and browsers.

## Results


### 99 only but...

The 100 score is not strictly reached because PageSpeed Insights indicates a score of 99/100. But if you look at the 2 remaining suggestions, these suggestions are not related to the project per se.

*Suggestions Summary*

```
Leverage browser caching for the following cacheable resources:
http://www.google-analytics.com/analytics.js (2 hours)
```

We do not have the ability to change the caching policy of this JavaScript file hosted by Google and we do not want to remove our analytics tools.

```
Minify JavaScript for the following resources to reduce their size by 677B (1% reduction).
Minifying http://hit100perf-env.elasticbeanstalk.com/app.js could save 677B (1% reduction) after compression.
```

PageSpeed Insights suggests that there still is 1% reduction left on our JavaScript file. The only way for us to get this 1% left would be to use the same minification algorithms that Google use to analyse our file. Google suggests in its documentation the following tools Closure Compiler, JSMin or YUI Compressor. We are using the webpack plugin UglifyJsPlugin based on Uglify.

### Timeline
