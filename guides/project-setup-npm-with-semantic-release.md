# Setting up a new NPM based project using semantic release
This setup is a continuous release setup, as soon as anything worth releasing (ie, not a chore) it will be pushed automatically to NPM.

## Requirements
* [Travis CLI](https://github.com/travis-ci/travis.rb#installation)

## Standard Node project setup
We have standardised on a number of tools, and much of this is based on [this blog post](https://hackernoon.com/these-6-essential-tools-will-maintain-your-npm-modules-for-you-4cbbee88e0cb)

* Travis CI
* Semantic Release
* Greenkeeper

### Instructions
#### 1. Create verify package.json script
To build, lint and run tests you should be able to just run `yarn verify`

#### 2. Setup .travis.yml

```
language: node_js
node_js:
    - lts/*
cache: yarn
notifications:
    email: false
script: yarn verify
jobs:
    include:
        - stage: release
          node_js: lts/*
          deploy:
              provider: script
              skip_cleanup: true
              script:
                  - npx semantic-release
```

#### 3. Add NPM/GitHub tokens
Add tokens to global environmental variables (note encrypted values are not available to insecure builds (Pull requests etc)

NOTE: The npm token you use will get an email to it’s account every time the package is published 

``` sh
travis encrypt GH_TOKEN=<github token> --add --com 

travis encrypt NPM_TOKEN=<npm token> --add --com
```

