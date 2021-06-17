# RebelCode - PSR7

[PSR-7] message implementation that also provides common utility methods.

This package is an informal fork of [guzzlehttp/psr] v1.8.2, with the following changes:

1. The root namespace is renamed to `RebelCode`
2. The target PHP version is lowered to 7.1

Some other package-level changes include tweaks to the Psalm config and using Docker for testing and building.

# Motivation

RebelCode develops WordPress plugins, one of which previously depended on [guzzlehttp/guzzle]. Due to a lack of
dependency management in WordPress, this dependency caused numerous conflicts with plugins from other vendors that also
depended on [guzzlehttp/guzzle] but at a different version.

Autoloading Guzzle meant that only one of the plugins that is active on a WordPress site could load Guzzle. The other
plugins would be using that autoloaded version of Guzzle, without being aware of it. This causes errors when, for
example, a plugin depends on Guzzle v6.x but the autoloaded version of Guzzle is v7.x.

As such, this package exists so that RebelCode's existing Guzzle dependents can replace Guzzle with an alternative
implementation, all the while benefiting from the tried-and-tested code that Guzzle relies on. This is also the reason
why the PHP version requirement was downgraded to 7.1.

See [rebelcode/wp-http] for a [PSR-18] compliant implementation that uses this package and the WordPress HTTP API.

Credits for this package go mostly to the Guzzle team ✌

# Installation

```
composer require rebelcode/psr7
```

[PSR-7]: https://www.php-fig.org/psr/psr-7

[PSR-18]: https://www.php-fig.org/psr/psr-18

[rebelcode/wp-http]: https://github.com/rebelcode/wp-http

[guzzlehttp/psr]: https://github.com/guzzle/psr7

[guzzlehttp/psr]: https://github.com/guzzle/guzzle
