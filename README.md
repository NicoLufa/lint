# lint

![image](http://cd7725b922b3176ce112-4476401cd1c8925765caec45a8dba466.r6.cf2.rackcdn.com/lint/lint.png)

[![Latest Stable Version](https://poser.pugx.org/dprevite/lint/v/stable.png)](https://packagist.org/packages/dprevite/lint) [![Total Downloads](https://poser.pugx.org/dprevite/lint/downloads.png)](https://packagist.org/packages/dprevite/lint) [![Latest Unstable Version](https://poser.pugx.org/dprevite/lint/v/unstable.png)](https://packagist.org/packages/dprevite/lint) [![License](https://poser.pugx.org/dprevite/lint/license.png)](https://packagist.org/packages/dprevite/lint)

A command line tool to lint your PHP code for syntax errors. Run it from the command line or from your build script.


## Usage

    usage: lint [-qb] [path]

    options:
      -q, --quiet:     disable verbose output
      -b, --blame:     display git blame along with error messages
      --exclude:       comma separated list of folder patterns to exclude
      -h, --help:      display this help screen

**Examples**

Find who caused a syntax error: (git is required)

    $ lint -b ../filename.php
    Linting files against PHP 7.0.6

    E
    1 files checked, 1 errors.
    PHP Parse error:  syntax error, unexpected ';' in filename.php on line 5
         Caused by Dan Previte <dprevite@example.com>


Check files, but ignore certain patterns to speed up the test:

    $ lint --exclude=*views*
    Linting files against PHP 7.0.6

    ............................................................
    ............................................................
    ................................................E...........
    180 files checked, 1 errors.
    PHP Parse error:  syntax error, unexpected ';' in filename.php on line 26
         Caused by Dan Previte <dprevite@example.com>

## Install

### Composer

    composer require dprevite/lint


### One Line Installer

    wget https://raw.githubusercontent.com/dprevite/lint/master/scripts/lint && sudo mv lint /usr/local/bin/lint && sudo chmod 0755 /usr/local/bin/lint

