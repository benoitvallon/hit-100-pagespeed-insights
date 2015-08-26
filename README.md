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

## Timeline

### Beanstalk default application

We reached here a pretty good result because the page is very simple without any JavaScript or complex CSS. The page is even so simple that it doesn't handle mobile devices and gets a bad scrore at usability.

![desktop version](https://github.com/benoitvallon/hit-100-pagespeed-insights/blob/master/results/v1-beanstalk-default-app/desktop.png "Desktop version")

![Mobile version](https://github.com/benoitvallon/hit-100-pagespeed-insights/blob/master/results/v1-beanstalk-default-app/mobile.png "Mobile version")

### React Starter kit default application

The score reached by the React Starter kit default application is very bad mostly because the project hasn't been build in production mode. But one important thing that we can notice is that the compression doesn't seem to be activated and this parameter is not likely to be activated even if we change the build parameter.

![desktop version](https://github.com/benoitvallon/hit-100-pagespeed-insights/blob/master/results/v2-starter-kit-default-app/desktop.png "Desktop version")

![Mobile version](https://github.com/benoitvallon/hit-100-pagespeed-insights/blob/master/results/v2-starter-kit-default-app/mobile.png "Mobile version")

### With compression activated

Once the compression has been activated we can see that only it remains suggestions that seem to be related to the build method.

![desktop version](https://github.com/benoitvallon/hit-100-pagespeed-insights/blob/master/results/v3-express-compression-activated/desktop.png "Desktop version")

![Mobile version](https://github.com/benoitvallon/hit-100-pagespeed-insights/blob/master/results/v3-express-compression-activated/mobile.png "Mobile version")

### Build with the production parameter

Here we are 99... Read above in the results section if you want to know why we consider this 99 as 100.

![desktop version](https://github.com/benoitvallon/hit-100-pagespeed-insights/blob/master/results/v4-build-for-production/desktop.png "Desktop version")

![Mobile version](https://github.com/benoitvallon/hit-100-pagespeed-insights/blob/master/results/v4-build-for-production/mobile.png "Mobile version")
