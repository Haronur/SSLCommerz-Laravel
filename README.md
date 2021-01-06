<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[Curotec](https://www.curotec.com/)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

## SSLCommerz-Laravel
- Consult the Laravel docs on database configuration and ensure you have a working database set up.
#### Create Database at phpMyAdmin named `sslcommerz-laravel` and setup `.env` file in your root directory 

- Database
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=sslcommerz-laravel
DB_USERNAME=root
DB_PASSWORD=
```
- Run database migrations to create the users table:
```
php artisan migrate
```
Core Library Directory Structure
```
 |-- config/
    |-- sslcommerz.php
 |-- app/Library/SslCommerz
    |-- AbstractSslCommerz.php (core file)
    |-- SslCommerzInterface.php (core file)
    |-- SslCommerzNotification.php (core file)
 |-- README.md
 |-- orders.sql (sample)
```
Instructions:

    Step 1: Download and extract the library files.

    Step 2: Copy the Library folder and put it in the laravel project's app/ directory. If needed, then run composer dump -o.

    Step 3: Copy the config/sslcommerz.php file into your project's config/ folder.

Now, we have already copied the core library files. Let's do copy some other helpers files that is provided to understand the integration process. The other files are not related to core library.

    Step 4: Add STORE_ID and STORE_PASSWORD values on your project's .env file. You can register for a store at https://developer.sslcommerz.com/registration/

    Step 5: Copy the SslCommerzPaymentController into your project's Controllers folder.

    Step 6: Copy the defined routes from routes/web.php into your project's route file.

    Step 7: Add the below routes into the $excepts array of VerifyCsrfToken middleware.

protected $except = [
    '/pay-via-ajax', '/success','/cancel','/fail','/ipn'
];

    Step 8: Copy the resources/views/*.blade.php files into your project's resources/views/ folder.

Now, let's go to the main integration part.

    Step 9: To integrate popup checkout, use the below script before the end of body tag.

## SSLcommerz with fixed
`php artisan make:Model Order -m`
```
    public function up()
    {
        Schema::create('orders', function (Blueprint $table) {
            $table->id();
            $table->string('name')->nullable();
            $table->string('email')->nullable();
            $table->string('phone')->nullable();
            $table->double('amount')->nullable();
            $table->longText('address')->nullable();
            $table->string('status')->nullable();
            $table->string('transaction_id')->nullable();
            $table->string('currency')->nullable();
            $table->timestamps();
        });
    }
```
- `php artisan migrate`
