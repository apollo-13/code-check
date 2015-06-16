# Code check #

Standard way, how to check code quality of the Apollo13 projects.

## Instalation ##

Preferred way for installation is via [Composer](https://getcomposer.org)

    composer require --dev apollo13/code-check

Because the package is proprietary, you have to add repository in your composer list.

    composer config -g repositories.code-check vcs git@bitbucket.org:apollo-13/code-check.git

For easy usage of this script add following piece of json code into the project `composer.json` file.

    "scripts": {
        "code-check": "code-check src"
    }

Directory to be checked can be specified as first argument of the `code-check` script. By default *src* directory is checked.

## Usage ##

Easy way to run script is by the executing of the following command, when the project have added previous piece of json code in his `composer.json` file.

    composer run-script code-check

To prevent pushing wrong code into the company git repository, it is recommended to add git `pre-push` hook.

    ln -s ../../vendor/bin/code-check-pre-push .git/hooks/pre-push
