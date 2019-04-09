---
title: 'Installation'
date: 2019-04-08
weight: 10
description: Here's what you need to get started with Formgate.
---

- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)

# <a name="requirements"></a> Requirements

* PHP 7.2
* Web server supporting PHP
* Composer

# <a name="installation"></a> Installation

1. Host this repo on your web server (e.g. forms.yourdomain.com) by running `git clone https://github.com/formgate/formgate`
2. Ensure the `public` directory is configured as your document root.
3. Run `composer install` to download dependencies.
4. Copy `.env.example` to `.env`.
5. Run `php artisan key:generate` to generate your app key and continue configuration.

# <a name="configuration"></a> Configuration

One you have followed the installation options above it is time to configure Formgate. You should open your `.env` file and set up the variables as necessary. The `RECIPIENT_ALLOW_LIST` should contain a comma separated list of email addresses that can be used in the `_recipient` form field. If an email that is not in this list is used in the field then the email not send and an exception will be thrown.
