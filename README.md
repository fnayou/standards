Standards
=========

Clear and easy to use **PHP Code Sniffer** configurator.

Work with *symfony*, *laravel*, *yii* and any PHP based projects.

## Installation

via `composer` and for dev :

```bash
$ composer require --dev fnayou/standards
```

by default, you can run command from  `vendor/bin/standards`, but you can add :

```json
"config": {
    "bin-dir": "bin"
}
```

and you can run command from `bin/standards`.

note that you can install globally :

```bash
$ composer global require fnayou/standards
```

## Usage

### Using .standards configuration file

all you have to do is to create a dot file named `.standards` in which we will have all our parameters :

```
# .standards file content

# can be phpcs or phpcbf (optional - default: phpcs)
command=phpcs

# path used to load standards (optional)
#standard-path=path/to/phpcs/standards/

# standard used by PHP CodeSniffer (required)
standard=PSR2

# verbose/debug mode (optional - default: false)
#verbose=true

# allowed files and directories (optional)
src/

# ignored files and directories (optional)
!tests
```

now all you have to do is to run command `bin\standards`

### Running command with arguments

you can run command with [phpcs arguments](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Configuration-Options) :

```bash
$ bin/standards src  --standard=PSR2 --ignore=tests
```

> note that this use will override configuration using `.standards` file if used.

### With Symfony

you have to install via `composer` :

```bash
$ composer require --dev fnayou/standards
$ composer require --dev escapestudios/symfony2-coding-standard
```

and next, create your `.standards` file :

```
standard=vendor/escapestudios/symfony2-coding-standard/Symfony2

# white list of files and directories
src/

# black list of files and directories
!tests
```

now, all you have to do is to run command `bin\standards`.

### With Laravel

you have to install via `composer` :

```bash
$ composer require --dev fnayou/standards
$ composer require --dev pragmarx/laravelcs
```

and next, create your `.standards` file :

```
standard=vendor/pragmarx/laravelcs/Standards/Laravel

# white list of files and directories
src/

# black list of files and directories
!tests
```

now, all you have to do is to run command `bin\standards`.

### With Yii

you have to install via `composer` :

```bash
$ composer require --dev fnayou/standards
$ composer require --dev yiisoft/yii2-coding-standards
```

and next, create your `.standards` file :

```
standard=vendor/yiisoft/yii2-coding-standards/Yii2

# white list of files and directories
src/

# black list of files and directories
!tests
```

now, all you have to do is to run command `bin\standards`.

## Credits

- [Aymen FNAYOU][link-author] - [GitHub][link-author-github]
- Fork from the awesome [M6Web Coke][link-m6web-coke] so thanks ;)

## Notes

I have forked the wonderful [M6Web Coke][link-m6web-coke] because the company where I'm working
find that **coke** and **sniff** is not so conventional :( and they refused to used it.
And honestly I don't like blue in the output :P

## Todo

- generate `.standards` file
- handle different path for command (`phpcs` installed globally)

## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT) Please see [License File](LICENSE.md) for more information.

[link-author]: https://aymen-fnayou.com
[link-author-github]: https://github.com/fnayou
[link-m6web-coke]: https://github.com/M6Web/Coke
