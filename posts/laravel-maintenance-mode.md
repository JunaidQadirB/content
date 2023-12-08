---
Image: https://res.cloudinary.com/benjamincrozat-com/image/fetch/c_scale,f_webp,q_auto,w_1200/https://github.com/benjamincrozat/content/assets/3613731/827ff581-35ec-4cef-a704-7a0d278e6441
Title: Master Laravel's maintenance mode
Description: The maintenance mode is like putting a "Be right back!" sign on your website. Learn how to get it going.
Canonical: 
Audio:
Published at: 2023-12-07
Categories: laravel
---

## Enabling Laravel's maintenance mode

When it’s time to update your app or perform some maintenance, switching to maintenance mode is super handy. And yet, I always forget it exists. 🤦‍♂️

The maintenance mode is like putting a "Be right back!" sign on your website. To get this going in Laravel, it's as simple as running a command:

```bash
php artisan down
```

What if you want to give users a heads up that the site will be back shortly? Just add a refresh option:

```bash
php artisan down --refresh=15
```
 
This will tell the user's browser to reload the page after 15 seconds.

![Laravel's maintenance mode in action.](https://res.cloudinary.com/benjamincrozat-com/image/fetch/c_scale,f_webp,q_auto,w_1200/https://github.com/benjamincrozat/content/assets/3613731/ecb02026-0087-4201-89ca-c747c45702e9)

## Sneaking past maintenance mode

Now, here's a cool trick. You can bypass maintenance mode with a secret token. Create a token using:

```bash
php artisan down --secret="your-secret-token"
```

Visit your app’s URL with the token appended (http://example.test/WeHrMT6odmCLXWkE for example), and you’ll get a bypass cookie. 

And if you prefer the framework to create a token for you, version 10.35 lets you do this:

```bash
php artisan down --with-secret
```

Just remember, keep that secret simple and URL-friendly.

## Pre-rendering the Laravel's maintenance view

Want to avoid errors when users hit your site mid-update? You can pre-render a maintenance view that shows up instantly:

```bash
php artisan down --render="errors::503"
```

This is served up before Laravel fully boots, so it's quick to the draw.

(Oh and by the way, if you forgot about it, the 503 HTTP code means "Service Unavailable," hence the need to render this error page.)

## Redirects during maintenance

Maybe you'd rather redirect users elsewhere while you tidy up. No problem:

```bash
php artisan down --redirect=/
```

This steers visitors to wherever you specify.

## Disabling maintenance mode

All done? Great, let’s bring your app back with:

```bash
php artisan up
```

And just like that, you’re live again!

## Customize Laravel's maintenance page

You’re the boss when it comes to how your maintenance page looks. Set up your own template at `resources/views/errors/503.blade.php` and make it your own.

## What about queued jobs during maintenance mode?

Worry not; queued jobs are put on pause in maintenance mode. They'll pick up right where they left off once you're back in action.
