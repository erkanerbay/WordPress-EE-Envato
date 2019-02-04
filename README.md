# EE WordPress Coding Standards

This package contains two WordPress Coding Standards for PHP_CodeSniffer.

For agency works use WordPress-EE. Base sniff is WordPress-Extra.

For Envato products use WordPress-EE-Envato. Base sniffs are WordPress-Docs and WordPress-Extra.

## Differences from WordPress Coding Standards

- Tabs should represent 2 spaces
- Ignore alignment with surrounding assignments
- Add checking for unused function parameters
- Array indentation 2 spaces
- Allow theme hierarchy specific file name exceptions
- Forbidden space after function keyword and open parenthesis
- Ignore unused parameters in functions on account on hooks
- Don't worry about files that don't contain any code
- Don't use Yoda conditions

## Requirements

The WordPress Coding Standards require PHP 5.4 or higher and PHP_CodeSniffer version 3.3.1 or higher.
To set up coding standarts be sure to install [composer](https://getcomposer.org/) first, then check your environment variables.

```
composer global require "squizlabs/php_codesniffer=*"
```

Make sure you have the composer bin dir in your PATH. The default value is ~/.composer/vendor/bin/,
but you can check the value that you need to use by running

```
composer global config bin-dir --absolute
```

for windows it should print out.

```
C:\Users\User\AppData\Roaming\Composer/vendor/bin
```

## Printing a List of Installed Coding Standards

PHP_CodeSniffer can print you a list of the coding standards that are installed so that you can correctly specify a coding standard to use for testing. You can print this list by specifying the -i command line argument.

```
phpcs -i
```

## Phpcs Standarts Folder Path

Windows:

```
C:\Users\User\AppData\Roaming\Composer\vendor\squizlabs\php_codesniffer\src\Standards
```

## Install WordPress Coding Standarts

cd desktop then use composer to install wpcs

```
composer create-project wp-coding-standards/wpcs --no-dev
```

copy WordPress, WordPress-Core, WordPress-Docs, WordPress-Extra folders to standarts folder.

Description of each sniffs:

- **WordPress-Core** - main ruleset for WordPress core coding standards
- **WordPress-Docs** - additional ruleset for WordPress inline documentation standards
- **WordPress-Extra** - extended ruleset for recommended best practices, not sufficiently covered in the WordPress core coding standards
  includes WordPress-Core

Setting WordPress-Extra for phpcs default standart config

```
phpcs --config-set default_standard WordPress-Extra
```

Setting WordPress-EE for phpcs default standart config

```
phpcs --config-set default_standard WordPress-EE-Envato
```

Check phpcs current default standard

```
phpcs --config-show
```

## IDE

You dont need this for it to work. Coz we already set it as default standard.

### Sublime Text 3

```
"phpcs": {
    "@disable": false,
    "args": [],
    "excludes": [],
    "standard": "WordPress-EE"
},
```

### Visual Studio Code

```
"phpcs.enable": true,
"phpcs.standard": "WordPress-EE",
```

## Ignoring

// @codingStandardsIgnoreLine
// PHPCS: XSS ok.
// phpcs:ignore Squiz.ControlStructures.ControlSignature.NewlineAfterOpenBrace

###### note

This moved from bitbucket acc2.
