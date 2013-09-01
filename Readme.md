Travis simulator so you do not need to wait for the build.<br/>
Reads your .travis.yml and runs what travis would run.

![Results](http://dl.dropbox.com/u/2670385/Web/wwtd-results.png)

Install
=======

```Bash
gem install wwtd
```

Usage
=====

```Bash
wwtd
START gemfile: gemfiles/rails32.gemfile, rvm: 2.0
....
START gemfile: gemfiles/rails32.gemfile, rvm: 1.9.3
....
Results:
SUCCESS gemfile: gemfiles/rails32.gemfile, rvm: 2.0
FAILURE gemfile: gemfiles/rails32.gemfile, rvm: 1.9.3
```

### Parallel

 - might show errors that do not happen in serial builds
 - runs number-of-processors builds in parallel
 - runs each configuration in a separate process
 - adds `ENV["TEST_ENV_NUMBER"]` (1 = "" 2 = "2") so you can do `db = "test#{ENV['TEST_ENV_NUMBER']}"`

```Bash
wwtd --parallel
same result, but number-of-processors faster :)
```

Author
======
[Michael Grosser](http://grosser.it)<br/>
michael@grosser.it<br/>
License: MIT<br/>
[![Build Status](https://travis-ci.org/grosser/wwtd.png)](https://travis-ci.org/grosser/wwtd)
