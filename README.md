# laravel-blog
  A simple Blog Module for Laravel 5
  
## Features
  - Create/update/delete posts.
  - Add different category of blog. Create blog in different category. 
  - Bundled migration for building the database schema
  - Facebook API integration. Share/Like on Facebook.
  - Twitter API integration. Share on Twitter.
  - Google+ API integration. Share on Google+.
  - Infinite ajax scroller. No need to click on next page.
  - You can customise it as per your requirements.
  

## Installation
1. Create a file called `module.php` inside the `config` directory. 
   Add following code in module.php. 

   ````
    return  [
        'modules' => [
           'Blog',
        ]
    ];
   ```

   You can add more then one modules inside `modules` array.  
2. Open up the file `config/app.php` and add `'App\Modules\ModulesServiceProvider',` to the end of the providers array.
   
    ```
    'providers' => [
        App\Modules\ModulesServiceProvider::class,
    ]
   ```
    
3. Create new folder called `Modules` inside app directory.
4. Add `Blog` folder inside Modules directory. App directory structure look like this:

   ```
      app/
      |---Modules
          |---Blog
              |---Assets
              |---Components
              |---Controllers
              |---Middleware
              |---Migrations
              |---Models
              |---Views
              |---BlogServiceProvider.php
              |---routes.php
          |---ModulesServiceProvider.php
   ```
   
   
5. Head to the Modules directory and add a file called `ModulesServiceProvider.php`
6. Run Migrations. For that use following command.

   ```
	$ php artisan migrate --path app/Modules/Blog/Migrations
   ```
   (Role column will be added into your users table. That will be define which user has author/admin role. You can change table name as per your requirement.)
7. To set Facebook API key open up Blog/Views/layouts/app.blade.php and
    set 

   ```
    appId      : 'your app id',
   ``` 
   in line number 8.
8. To set Twitter key open up Blog/Views/posts/show.blade.php and
    set 

   ```
    data-via : 'Your twitter id'
   ``` 	   
   in line number 187.
9. For Routes you can add/update in Blog/routes.php
   (Blog module has its own routes.php so you can add/update routes here.)

10. Please run `composer autoload` if you get any error
