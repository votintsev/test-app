## Start Local Machine
1. Clone the repository:
```
git clone git@github.com:vivox-ai/zero.git
```
2. **Prepare your environment**. We use [Laravel Sail](https://laravel.com/docs/sail) for our development environment.
    - Go to folder `cd zero`
    - Run the following command to set up your environment:
        ```bash
        docker run --rm \
            -u "$(id -u):$(id -g)" \
            -v "$(pwd):/var/www/html" \
            -w /var/www/html \
            laravelsail/php83-composer:latest \
            composer install --ignore-platform-reqs

    - Copy `env.example` to `.env`:
         ```bash
         cp .env.example .env
         ```
    - It's recommended to add an alias to your `.bashrc` or `.zshrc` file for easier use of the Sail command. Add the following line:
      ```bash
      # Aliases for Laravel Sail
      alias sail='[ -f sail ] && bash sail || bash vendor/bin/sail'
      ```
      After adding this alias, you can use the `sail` command without the `./vendor/bin/` prefix.
    - Start the Sail services:
         ```bash
         sail up -d
         ```
    - Run migrations:
         ```bash
         sail artisan migrate
         ```
    - Install Node.js packages:
         ```bash
         sail npm i
         ```
    - Add secrets to `.env` - skipped for now
    - Start frontend
        ```
         sail npm run dev
        ```
    - Open [localhost](http://localhost)

### Everyday Workflow
```
sail up -d
sail npm run dev
```

<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 2000 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.
