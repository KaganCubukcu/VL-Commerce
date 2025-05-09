<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About This Project: E-commerce Application

This is a full-stack e-commerce application built with the TALL stack (Tailwind CSS, Alpine.js, Laravel, Livewire - though in this case, Vue.js with Inertia.js is used instead of Livewire/Alpine.js for the frontend) and Docker (Laravel Sail). The primary goal of this project is to practice backend development concepts, strengthen SQL database skills, and manage a product catalog.

**Key Technologies Used:**

*   **Backend:** Laravel (PHP)
*   **Frontend:** Vue.js with Inertia.js
*   **Database:** MySQL
*   **Development Environment:** Docker (Laravel Sail)
*   **Authentication:** Laravel Jetstream

## Learning Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Project Setup Instructions

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/KaganCubukcu/VL-Commerce
    cd e-commerce
    ```

2.  **Copy `.env.example` to `.env`:**
    ```bash
    cp .env.example .env
    ```

3.  **Install Composer dependencies and bring up Docker containers with Laravel Sail:**
    The first command ensures Sail can execute properly if it's the first time.
    ```bash
    docker run --rm \
        -u "$(id -u):$(id -g)" \
        -v "$(pwd):/var/www/html" \
        -w /var/www/html \
        laravelsail/phpXX-composer:latest \
        composer install --ignore-platform-reqs
    ```
    *(Replace `phpXX-composer` with the PHP version your project uses, e.g., `php83-composer` if you are on PHP 8.3)*

    Alternatively, if you have Composer installed locally and prefer, you can run `composer install` first, then start Sail.

4.  **Start Laravel Sail containers:**
    ```bash
    ./vendor/bin/sail up -d
    ```

5.  **Generate Application Key:**
    ```bash
    ./vendor/bin/sail artisan key:generate
    ```

6.  **Run Database Migrations:**
    ```bash
    ./vendor/bin/sail artisan migrate
    ```

7.  **Install NPM dependencies and build frontend assets:**
    ```bash
    ./vendor/bin/sail npm install
    ./vendor/bin/sail npm run build
    ```
    (Or `npm run dev` for development with hot reloading)

8.  **Access the application:**
    Open your browser and navigate to `http://localhost:PORT` (the port is defined as `APP_PORT` in your `.env` file, or by the `ports` section for `laravel.test` in `docker-compose.yml` - we set it to `8000` earlier).

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Redberry](https://redberry.international/laravel-development/)**
- **[Active Logic](https://activelogic.com)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
