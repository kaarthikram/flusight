![icon](./icon.png)

Flusight is a static influenza forecasts visualizer. It takes weekly prediction
files in the
[format]((https://github.com/cdcepi/FluSight-forecasts/blob/master/2016-2017_submission_template.csv))
used by [CDC FluSight Challenge](https://predict.phiresearchlab.org/), extracts
entities needed for visualization and generates a minified webpage ready for
static hosting. The visualizer uses an intermediate file, summarizing the
predictions, which can be generated either by the set of scripts in the
repository (which uses CDC's prediction format) or by the user.

The live version associated with this github
repository
at [https://reichlab.github.io/flusight/](https://reichlab.github.io/flusight/)
displays predictions for CDC FluSight Challenge
by [Reich Lab](https://reichlab.github.io/) at UMass Amherst.

[![Standard - JavaScript Style Guide](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

[![DOI](https://zenodo.org/badge/69420249.svg)](https://zenodo.org/badge/latestdoi/69420249)
[![Build Status](https://travis-ci.org/reichlab/flusight.svg?branch=master)](https://travis-ci.org/reichlab/flusight)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/reichlab/flusight.svg)](https://github.com/reichlab/flusight/pulls)

![screenshot](screenframe.png)

## Quickstart

For submitting weekly predictions on
this [repository](https://github.com/reichlab/flusight) the recommended method
is to create a pull request on the master branch. Fork this project and add your
`.csv` files in `./data/` directory as described in the project’s
workflow [wiki](https://github.com/reichlab/flusight/wiki/Workflow). The pull
requests will be automatically built and once merged to master, will be deployed
to the website.

## Build it yourself

Flusight works as a static webpage and needs a static hosting service (like
github’s). Building the project and bundling data files
requires [node.js](https://nodejs.org/en/download/)
and [yarn](https://yarnpkg.com/en/docs/install) (you could
use [npm](https://www.npmjs.com/) too).

+ Clone this repository

  `git clone git@github.com:reichlab/flusight.git && cd ./flusight`

+ Install dependencies (you only need to run this when first installing the app)

  `yarn`
  
+ Put prediction submission files in `./data` as described in
  the [wiki](https://github.com/reichlab/flusight/wiki/Workflow)

+ Parse prediction files to generate `./src/assets/data.json` (summary file,
  used by the visualizer)

  `yarn run parse`
  
+ Test

  `yarn run test`
  
+ Bundle production build

  `yarn run build`

+ Host it somewhere. Copy over contents from `./dist` to your hosting service.

+ Alternatively, a quick deploy to github pages can be done by running
  
  `yarn run deploy`
  
  *Remember to point `git remote origin` to the repository where you want the
  deployment to take place*
  
  
In case you want to generate the `./src/assets/data.json` file yourself, you can
replace the parsing step (`yarn run parse`) with your own but make sure to check
for schema compliance (`yarn run test`). Head over to
the [wiki](https://github.com/reichlab/flusight/wiki) to know more.

## Development

> On this repository, commits to `master` are automatically built and deployed
> to `gh-pages` with travis. `master` contains most recent *working* version.
> `develop` contains the latest commits.

``` shell
# serve with hot reload at localhost:8080
yarn run dev

# build for production with minification
yarn run build
```

Go to the
development [wiki](https://github.com/reichlab/flusight/wiki/Development) for
more details.

## Contributing
Contributions are welcome. Use
the github [issue tracker](https://github.com/reichlab/flusight/issues) to
submit issues. Submit pull
requests [here](https://github.com/reichlab/flusight/pulls).
