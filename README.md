# Perfecty Push WP Plugin ⚡️

![tests](https://github.com/rwngallego/perfecty-push-wp/workflows/tests/badge.svg)
[![License](https://img.shields.io/badge/license-GLPv2-blue.svg)](./LICENSE.txt)

Self-hosted Push Notifications from your own Wordpress server for free! 🥳

**Perfecty Push WP** is a Wordpress plugin for **Perfecty Push**, an Open Source project that allows you to send Web Push notifications
directly from your own server: No hidden fees, no third-party dependencies and you
own your data. 👏

## Features ✨

- Open Source and self-hosted
- No third-party dependencies when self-hosted
- Offline browser notifications through [Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API) (Safari is not supported yet)
- You retain and own the user authorization tokens
- WordPress plugin with a built-in Push Server based on [web-push-php](https://github.com/web-push-libs/web-push-php)

## Requirements 🧩

- `PHP 7.1+`
- The `gmp` extension.

**Note**: Support for `PHP 7.1` will be drop in the mid-term, so the `gmp` extension
will be optional and recommended only for better performance.
The supported PHP version will start from `7.2+`.

## Local development 👨🏻‍💻

To see it in action in your local development enviroment, you need a set of
services which Wordpress relies on. You start off by creating the docker image:

```
docker build -t custom-wordpress:5.2.3-php7.1-apache .
```

Then start all the services and run the setup:

```
make up
make setup
```

You can now go to http://localhost/wp-login.php > Plugins > Activate the
**Perfecty Push** plugin.

![Screenshot preview](https://github.com/rwngallego/perfecty-push-wp/raw/master/.github/assets/perfecty.gif "Preview")

## Available commands 👾

```
# start the service containers
make up

# stop de service containers
make down

# remote console
make console

# run the unit tests
make test

# setup all: make wordpress, make composer, make phpunit
make setup

# setup wordpress and plugins
make wordpress

# install all the composer dependencies
make composer

# setup wordpress as a testing environment for phpunit
make phpunit
```

## Testing ✅

This project relies on automated tests as in the [Wordpress Core](https://make.wordpress.org/core/handbook/testing/automated-testing/writing-phpunit-tests/) guidelines.

Run all the test suites:

```
make test
```

Run a single test:

```
make console
cd wp-contents/plugins/perfecty-push/
phpunit --filter test_schedule_broadcast_async
```

## License 👓

The WordPress Plugin is an Open Source project licensed under [GPL v2](./LICENSE.txt).

## Collaborators 🔥

[<img alt="rwngallego" src="https://avatars3.githubusercontent.com/u/691521?s=460&u=ceab22655f55101b66f8e79ed08007e2f8034f34&v=4" width="117">](https://github.com/rwngallego) |
:---: |
[Rowinson Gallego](https://www.linkedin.com/in/rwngallego/) |