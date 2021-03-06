A better pre-commit hook for git.

## Installation

Install the gem

    $ gem install pre-commit

Use the pre-commit command to generate a stub pre-commit hook

    # In your git repo
    $ pre-commit install

This creates a .git/hooks/pre-commit script which will check your git config and run checks that are enabled.

## Configuration

These are the available checks:

* white_space
* console_log
* debugger
* tabs
* jshint
* js\_lint\_all (Runs JSLint on all staged JS files)
* js\_lint\_new (Runs JSLint on all new staged JS files)
* closure\_syntax\_check
* php (Runs php -l on all staged files)
* ruby_symbol_hashrockets (1.9 syntax. BAD :foo => "bar". GOOD foo: "bar")

To configure which checks you would like to run, simply set the `pre-commit.checks` git configuration setting. 

To enable `white_space` and `tab` checks:

    # From your git repo
    $ git config "pre-commit.checks" "white_space, tabs"

To enable `white_space`, `console_log` and `debugger` checks:

    # From your git repo
    $ git config "pre-commit.checks" "white_space, console_log, debugger"

Note: If no checks are configured, a default set of checks is run:

    white_space, console_log, debugger, tabs, jshint, migrations
