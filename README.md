# Very short description of the package

[![Latest Version on Packagist](https://img.shields.io/packagist/v/adr1enbe4udou1n/vtec-crud.svg?style=flat-square)](https://packagist.org/packages/adr1enbe4udou1n/:package_name)
[![GitHub Tests Action Status](https://img.shields.io/github/workflow/status/adr1enbe4udou1n/vtec-crud/run-tests?label=tests)](https://github.com/adr1enbe4udou1n/:package_name/actions?query=workflow%3Arun-tests+branch%3Amaster)
[![Total Downloads](https://img.shields.io/packagist/dt/adr1enbe4udou1n/vtec-crud.svg?style=flat-square)](https://packagist.org/packages/adr1enbe4udou1n/:package_name)


This is where your description should go. Try and limit it to a paragraph or two. Consider adding a small example.

## Support us

We invest a lot of resources into creating [best in class open source packages](https://adr1enbe4udou1n.be/open-source). You can support us by [buying one of our paid products](https://adr1enbe4udou1n.be/open-source/support-us). 

We highly appreciate you sending us a postcard from your hometown, mentioning which of our package(s) you are using. You'll find our address on [our contact page](https://adr1enbe4udou1n.be/about-us). We publish all received postcards on [our virtual postcard wall](https://adr1enbe4udou1n.be/open-source/postcards).

## Installation

You can install the package via composer:

```bash
composer require vtec/crud
```

## Deps used

[spatie/laravel-medialibrary](https://github.com/spatie/laravel-medialibrary)
[spatie/laravel-query-builder](https://github.com/spatie/laravel-query-builder)
[spatie/laravel-translatable](https://github.com/dimsav/laravel-translatable)
[symfony/yaml](https://github.com/symfony/Yaml/)

## Other recommended packages for admin

```bash
composer require laravel/ui laravel/sanctum doctrine/dbal itsgoingd/clockwork barryvdh/laravel-elfinder
php artisan ui:auth
php artisan elfinder:publish

php artisan vendor:publish --provider='Barryvdh\Elfinder\ElfinderServiceProvider' --tag=config
php artisan vendor:publish --provider='Barryvdh\Elfinder\ElfinderServiceProvider' --tag=views

php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
> Optional : remove migration
```

```
use Laravel\Sanctum\Http\Middleware\EnsureFrontendRequestsAreStateful;

'api' => [
    EnsureFrontendRequestsAreStateful::class,
    'throttle:60,1',
    \Illuminate\Routing\Middleware\SubstituteBindings::class,
],

>> cors
```

## Recommended dev packages

```bash
composer require barryvdh/laravel-ide-helper friendsofphp/php-cs-fixer laracasts/generators --dev
```

```bash
[--model=0]
php artisan make:migration:schema create_users_table --schema="username:string, email:string:unique"
php artisan make:migration:schema remove_user_id_from_posts_table --schema="user_id:integer"
php artisan make:migration:schema create_posts_table --schema="title:string, body:text, excerpt:string:nullable"
php artisan make:migration:schema remove_excerpt_from_posts_table --schema="excerpt:string:nullable"
php artisan make:migration:schema create_posts_table --schema="user_id:unsignedInteger:foreign, title:string, body:text"
php artisan make:migration:pivot tags posts
```

username:string
body:text
age:integer
published_at:date
excerpt:text:nullable
email:string:unique:default('foo@example.com')

## Usage

``` php
$crud = new Vtec\Crud();
echo $crud->echoPhrase('Hello, Vtec!');
```

## Testing

``` bash
composer test
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Security

If you discover any security related issues, please email freek@adr1enbe4udou1n.be instead of using the issue tracker.

## Credits

- [Adrien Beaudouin](https://github.com/adr1enbe4udou1n)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
