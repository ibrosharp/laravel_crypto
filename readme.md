# Service Starter

## Install

Add the following to your composer.json file

```
"repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/neo-bank/servicesetup.git"
        }
    ]
```

then run 

`$ composer require ibrodev/servicesetup`

## Features

- Provides and artisan command for creating private and public keys
- Encryt and Decrypts Request Automatically 

## Usage

Register the Service Provider on your Lumen/Laravel Application in `boostrap/app`

```php
$app->register(\Ibrodev\Servicesetup\ServiceSetupServiceProvider::class);
```

Add the Encription and Decryption middleware to the application in `boostrap/app`

```php
protected $middlewareGroups = [
    /*
    |--------------------------------------------------------------------------
    | Register Middleware
    |--------------------------------------------------------------------------
    |
    | Next, we will register the middleware with the application. These can
    | be global middleware that run before and after each request into a
    | route or middleware that'll be assigned to some specific routes.
    |
    */

    $app->middleware([
        \Ibrodev\Servicesetup\Middlewares\DecryptionMiddleware::class,
        \Ibrodev\Servicesetup\Middlewares\EncryptionMiddleware::class,
    ]);
];
```

Run the artisan command to generate a public and private key
```sh
php artisan initialize:service
```

## Testing

```bash
composer run test
```


## Credits

-   [Ibrahim Abdulsamad](https://github.com/ib-Jkid)

# License

The MIT License (MIT).

