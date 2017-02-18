# laravel-mix-stylus
Ready-to-go config for Laravel Mix and Stylus with plugins Nib, Jeet,Rupture.

# How to install
Just start with `npm install nib jeet rupture --save-dev`.

Then copy and paste to `webpack.mix.js` in Laravel 5.4 root directory the following code (replace the original one):
```
const { mix } = require('laravel-mix');

/*
 |--------------------------------------------------------------------------
 | Mix Asset Management
 |--------------------------------------------------------------------------
 |
 | Mix provides a clean, fluent API for defining some Webpack build steps
 | for your Laravel application. By default, we are compiling the Sass
 | file for the application as well as bundling up all the JS files.
 |
 */

mix.js('resources/assets/js/app.js', 'public/js')
   .stylus('resources/assets/stylus/app.styl', 'public/css',{ 
   		use: [
                require('rupture')(),
                require('nib')(),
                require('jeet')()
            ],
            import: [
                '~nib/index.styl',
                '~jeet/jeet.styl',
            ]
});
```

# Done
Thats all you need! 

Great thanks to *Jeffrey Way* [Laracasts maintainer](https://laracast.com):
This thing was given to me by *Jeff* on [support forum topic](https://laracasts.com/discuss/channels/elixir/laravel-54-mix-stylus).
