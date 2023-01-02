Step by Step to install Voyager and a Voyager Frontend 

**Prerequisites**
- PHP >= 7.2.3 or ^8.1
- PHP extension sqlite3 (required for teamtnt/tntsearch)
- Node & NPM
- Composer
- Laravel Requirements

# Installation
1. Install Laravel + Voyager (Replace the $VARs with your own values)

# 1.0 Install Laravel
- composer create-project --prefer-dist laravel/laravel $DIR_NAME

# 1.1 Require Voyager
- cd $DIR_NAME && composer require tcg/voyager

# 1.2 Copy .env.example to .env and update the DB & App URL config
- cp .env.example .env

# 1.3 Generate a Laravel key
- php artisan key:generate

# 1.4 Run the Voyager Installer
- php artisan voyager:install

# 1.5 Create a Voyager Admin User
- php artisan voyager:admin $YOUR_EMAIL --create

# **2. Install Voyager Frontend**

# 2.0 Require this Package in your fresh Laravel/Voyager project
- composer require pvtl/voyager-frontend

# 2.1 Run the Installer
- composer dump-autoload && php artisan voyager-frontend:install

# 2.3 Build the front-end theme assets
- npm run dev

# 2.4 Set the Laravel search driver in your .env
- echo "SCOUT_DRIVER=tntsearch" >> .env
