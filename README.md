# readme/metrics

Track your API metrics within ReadMe.

[![Build](https://github.com/readmeio/readme-php/workflows/CI/badge.svg)](https://github.com/readmeio/readme-php)

[![](https://d3vv6lp55qjaqc.cloudfront.net/items/1M3C3j0I0s0j3T362344/Untitled-2.png)](https://readme.io)

## Installation

```
composer require readme/metrics
```

## Usage

`readme/metrics` is currently targeted towards codebases utilizing Laravel. To get up and running, you'll need to do the following things:

1. Publish our config file into your `config/` directory:

```
php artisan vendor:publish --provider="ReadMe\ServiceProvider"
```

2. In `config/readme.php`, change `api_key` to the API key we provide to you in your ReadMe project on https://dash.readme.io.
3. Also in that config file, you'll need to change the `group` closure to return data relevant to your codebase and users. We've provided some simple defaults but you'll likely need to change them.

Once you've done all that, add `\ReadMe\Middleware::class` into your API middleware in `app/Http/Kernel.php` and API metrics will start streaming to your ReadMe project.
