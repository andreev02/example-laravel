<p align="center"><a href="http://app.itandreev.ru" target="_blank"><img src="https://i.imgur.com/beys0CS.jpg" width="800" alt="Laravel Logo"></a></p>



## Laravel example app

Hi there. This is an example Laravel SPA CRUD application with basic CRM concept. <br>
In a front Inertia & Vue3, Tailwind CSS.<br>
I created it for my resume. You can take it and edit for yourself as you wish.

> You can check it right here: http://app.itandreev.ru

## Dependencies

* PHP 8.2
* Laravel 10
* Database
* Redis
* Vue3 + Inertia

## Installation

There is a <b>Docker</b> in application you can compose it.

Or locally:
```
git clone https://github.com/andreev02/example-laravel.git

cd example-laravel

composer install
npm install

php artisan migrate
php artisan seed

npm run dev
php artisan serve
```
