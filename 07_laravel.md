# What is Laravel?
Laravel is a web application framework with expressive, elegant syntax. A web framework provides a structure and starting point for creating your application, allowing you to focus on creating something amazing while we sweat the details.  
Laravel is a free and open-source PHP web framework, created by Taylor Otwell and intended
for the development of web applications following the model–view–controller (MVC)
architectural pattern and based on Symfony. Some of the features of Laravel are a modular
packaging system with a dedicated dependency manager, different ways for accessing
relational databases, utilities that aid in application deployment and maintenance, and its
orientation toward syntactic sugar.
# Prerequisites for Laravel
* PHP - https://www.php.net/manual/en/
* MySQL - https://www.mysql.com/
* Apache - https://httpd.apache.org/  
Or We Can use web server solution package XAMPP
* XAMPP - https://www.apachefriends.org/download.html
* Composer - https://getcomposer.org/download/
* Node & NPM - https://nodejs.org/en/download/

# Create Laravel Project
you may create a new Laravel project via the Composer create-project command:  
```console
composer create-project laravel/laravel example-app
cd example-app
```
Or, you may create new Laravel projects by globally installing the Laravel installer via Composer:
```console
composer global require laravel/installer
laravel new example-app
```
After the project has been created, start Laravel's local development server using the Laravel's Artisan CLI serve command:
```console
cd example-app
php artisan serve
```
your application will be accessible in your web browser at `http://localhost:8000`.

# Routes
Web Routes can be defined in `routes/web.php`
```php
Route::get($uri, $callback);
Route::post($uri, $callback);
Route::put($uri, $callback);
Route::patch($uri, $callback);
Route::delete($uri, $callback);
Route::options($uri, $callback);
```

## Redirect Routes
If you are defining a route that redirects to another URI, you may use the `Route::redirect` method. This method provides a convenient shortcut so that you do not have to define a full route or controller for performing a simple redirect:
```php
Route::redirect('/here', '/there');
```
By default, `Route::redirect` returns a `302` status code. You may customize the status code
using the optional third parameter:
```php
Route::redirect('/here', '/there', 301);
```
## View Routes
If your route only needs to return a view, you may use the `Route::view` method.
```php
Route::view('/welcome', 'welcome');
```
The view method accepts a URI as its first argument and a view name as its second argument.
In addition, you may provide an array of data to pass to the view as an optional third argument
```php
Route::view('/welcome', 'welcome', ['name' => 'Taylor']);
```
## The Route List
The `route:list` Artisan command can easily provide an overview of all of the routes that are defined by your application:
```console
php artisan route:list
```
## Route Parameters
### Required Parameters
Sometimes you will need to capture segments of the URI within your route. For example, you may need to capture a user's ID from the URL. You may do so by defining route parameters:
```php
Route::get('/posts/{id}',[PostController::class, 'index']);
Route::get('/posts/{id}', function ($id) {
    return 'Post '.$id;
});
```
You may define as many route parameters as required by your route:
```php
Route::get('/posts/{id}/title/{title}', function ($id, $name) {
    return $id . ' & ' . $title;
});
```
### Optional Parameters
Occasionally you may need to specify a route parameter that may not always be present in the URI. You may do so by placing a ? mark after the parameter name. Make sure to give the route's corresponding variable a default value:
```php
Route::get('/post/{title?}', function ($title=null) {
    return $title;
});
Route::get('/post/{title?}', function ($title = 'John') {
    return $title;
});
```
### Named Routes
Named routes allow the convenient generation of URLs or redirects for specific routes. You may specify a name for a route by chaining the name method onto the route definition:
```php
Route::get('/post/title, function () {
    return 'something';
})->name('post');
```
You may also specify route names for controller actions:
```php
Route::get('/post/title', [PostController::class, 'show'])->name('post');
```
# Controllers
you can generate a controller by using `make:controller` artisan command
```console
php artisan make:controller PostController
```
you can generate a resource controller by using option `–-resource`
```console
php artisan make:controller PostController –resource
```
you can generate a resource controller with a model instance by using `–-model=Model`
```console
php artisan make:controller PostController --model=Post --resource
```
once you generate controller file, it is added to `app/Http/Controllers/UserController.php` and you can define a route to this controller like that:
```php
use App\Http\Controllers\PostController;
Route::get('/posts/{id}', [PostController::class, 'show']);
```
route resource can be defined as follows:
```php
use App\Http\Controllers\PostController;
Route::resource('posts', PostController::class);
```
Actions Handled By Resource Controller
|Verb|URI Action Route Name|
|----|---------------------|
|GET|/posts index posts.index|
|GET|/posts/create create posts.create|
|POST|/posts store posts.store|
|GET|/posts/{post} show posts.show|
|GET|/posts/{post}/edit edit posts.edit|
|PUT/PATCH|/posts/{post} update posts.update|
|DELETE|/posts/{post} destroy posts.destroy|
you can write a controller method as follows:
```php
<?php
namespace App\Http\Controllers;
use Illuminate\Http\Request;
class PostController extends Controller
{
    public function show($id)
    {
        return "hello";
    }
}
```
# Views
the views files are stored in `resources/views`.  
Create new file `resources/views/greeting.blade.php`   
in `greeting.blade.php`
```html
<h1>Hello</h1>
```
define a route in `web.php` to return a view
```php
Route::get('/', function () {
    return view('greeting');
});
```
# Blade Template
* Blade is the simple, yet powerful templating engine that is included with Laravel.
* Blade template files use the `.blade.php` file extension and are typically stored in the `resources/views` directory.
* Blade views may be returned from routes or controllers using the global view helper.
* Data may be passed to the Blade view using the view helper's second argument:
```php
Route::get('/', function () {
    return view('greeting', ['name' => 'John']);
});
```
## Displaying Data
You may display data that is passed to your Blade views by wrapping the variable in curly braces. For example, given the above route:  
You may display the contents of the name variable like so:
```php
Hello, {{ $name }}.
```
Blade's `{{ }}` echo statements are automatically sent through PHP's htmlspecialchars function to prevent XSS attacks.
Blade Directives
* You may construct if statements using the `@if`, `@elseif`, `@else`, and `@endif` directives. These directives function identically to their PHP counterparts:
* The `@auth` and `@guest` directives may be used to quickly determine if the current user is authenticated or is a guest:
* Switch statements can be constructed using the `@switch`, `@case`, `@break`, `@default` and `@endswitch` directives:
## Defining a Layout
```php
<!-- resources/views/layouts/app.blade.php -->
<html>
    <head>
        <title>App Name - @yield('title')</title>
    </head>
    <body>
        <div class="container">
            @yield('content')
        </div>
    </body>
</html>
```
## Extending a Layout
```php
<!-- resources/views/child.blade.php -->
@extends('layouts.app')
@section('title', 'Page Title')
@section('content')
    <p>This is my body content.</p>
@endsection
```
# Form
## csrf field
Cross-site request forgeries are a type of malicious exploit whereby unauthorized commands are performed on behalf of an authenticated user. Thankfully, Laravel makes it easy to protect your application from cross-site request forgery (CSRF) attacks.
```html
<form action="/profile" method="POST">
    @csrf
    ...
</form>
```
## method field
Since HTML forms can't make `PUT`, `PATCH`, or `DELETE` requests, you will need to add a hidden `_method` field to spoof these HTTP verbs. The `@method` Blade directive can create this field for you:
```php
<form action="/foo/bar" method="POST">
    @method('PUT')
    ...
</form>
```
## Validation Errors
The `@error` directive may be used to quickly check if validation error messages exist for a given attribute. Within an `@error` directive, you may echo the $message variable to display the error message:
```php
<!-- /resources/views/post/create.blade.php -->
<form action="/foo/bar" method="POST">
    @csrf
    <label for="name">Name:</label>
    <input type="text" id="name" name="name">
    @error('title')
        <div class="alert alert-danger">{{ $message }}</div>
    @enderror
</form>
```
# Laravel with bootstrap
install Laravel UI package before creating Auth Scaffolding using the below command.
```console
composer require laravel/ui
```
install bootstrap auth Scaffolding
```console
php artisan ui bootstrap --auth
```
install and run NPM packages
```console
npm install
npm run build
```
Now you have successfully completed Bootstrap Auth Scaffolding.
# Eloquent Model
To get started, let's create an Eloquent model. Models typically live in the `app\Models` directory and extend the `Illuminate\Database\Eloquent\Model` class. You may use the `make:model`
artisan command to generate a new model:
```console
php artisan make:model Post
```
If you would like to generate a database migrations when you generate the model, you may
use the `--migration` or `-m` option:
```console
php artisan make:model Post --migration
```
Generate a model and a migration, factory, seeder, and controller...
```console
php artisan make:model Post -mfsc
```
files will be added to `database/migrations/…` , `database/factories/…` , `database/seeders/…` ,
`app/Http/Controllers/…`
## Eloquent Relationships
for more info: https://laravel.com/docs/9.x/eloquent-relationships
### One to One
in User Model, we can define one to one relation:
```php
<?php
namespace App\Models;
use Illuminate\Database\Eloquent\Model;
class User extends Model
{
    /**
    * Get the phone associated with the user.
    */
    public function phone()
    {
        return $this->hasOne(Phone::class);
    }
}
$phone = User::find(1)->phone;
```
### One to Many
A one-to-many polymorphic relation is similar to a typical one-to-many relation; however, the child model can belong to more than one type of model using a single association.
```php
<?php
namespace App\Models;
use Illuminate\Database\Eloquent\Model;
class Post extends Model
{
    /** Get the comments for the blog post.*/
    public function comments()
    {
        return $this->hasMany(Comment::class);
    }
}
use App\Models\Post;
$comments = Post::find(1)->comments;
```
# Database Setup
database connection can be declared in `.env` file
```php
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=
```
## Database:Migrations
migration files located are in `database/migrations/…`
migration files can be created by `make:migration` command:
```console
php artisan make:migration create_posts_table
```
you can add more table column in migration file like that:
```php
public function up()
{
    Schema::create('posts', function (Blueprint $table) {
        $table->id();
        $table->string('title');
        $table->text('about');
        $table->timestamps();
    });
}
```
others available types: `https://laravel.com/docs/9.x/migrations#available-column-types`  

## Running Migration
To run all of your outstanding migrations, execute the migrate Artisan command:
```console
php artisan migrate
```
Roll Back & Migrate Using A Single Command
The `migrate:refresh` command will roll back all of your migrations and then execute the migrate command. This command effectively re-creates your entire database:
```console
php artisan migrate:refresh
```
## Database:Seeding
Laravel includes the ability to seed your database with data using seed classes. All seed classes are stored in the database/seeders directory.  
To generate a seeder, execute the `make:seeder` Artisan command. All seeders generated by the framework will be placed in the `database/seeders` directory:
```console
php artisan make:seeder PostSeeder
```
and new seeder file is added in `database/seeders/PostSeeder.php`
```php
public function run()
{
    DB::table('post')->insert([
        'title' => "This is first Post",
        'about' => "This is the about of first post. Find more information here",
    ]);
}
```
and you can insert data into database via `db:seed` Artisan command.
```console
php artisan db:seed
```
and one row of data is inserted into your database table.

## Using Model Factories
you can also use model factories to generate large amount of database records.  
To create a factory, execute the `make:factory` artisan command:
```console
php artisan make:factory PostFactory
```
The new factory class will be placed in your `database/factories` directory.
in `databse/factories/StudentFactory`:
```php

protected $model = Post::class;
public function definition()
{
    return [
        'title' => fake()->title(),
        'about' => fake()->paragraph(),
    ];
}
```
in `database/seeders/StudentSeeder.php`
```php
use App\Models\Post;
public function run()
{
    Post::factory()->count(10)->create();
}
```
and you can insert data into database via `db:seed` Artisan command.
```console
php artisan db:seed
```
you will see 10 rows of random data are inserted into the table.

# Route Model Binding
When injecting a model ID to a route or controller action, you will often query the database to retrieve the model that corresponds to that ID. Laravel route model binding provides a convenient way to automatically inject the model instances directly into your routes. For example, instead of injecting a user's ID, you can inject the entire User model instance that matches the given ID.  
Laravel automatically resolves Eloquent models defined in routes or controller actions whose
type-hinted variable names match a route segment name. For example:
```php
use App\Models\Post;
Route::get('/posts/{post}', function (Post $post) {
    return $post->title;
});
```

# API With Laravel
Create a Post Model with migration:
```console
php artisan make:model Todo -m
```
update the migration table as follows:
```php
public function up()
{
    Schema::create('todos', function (Blueprint $table) {
        $table->id();
        $table->string('title');
        $table->longText('description');
        $table->timestamps();
    });
}
```
add fillable property in Model:
```php
class Todo extends Model
{
    use HasFactory;
    protected $fillable = ['title', 'description'];
}
```
and create API PostController relate to model Post inside Api folder
```console
php artisan make:controller Api\TodoController --model=Todo
```
inside `Api/PostController`, you can add index method as follows:
```php
class TodoController extends Controller
{
    /**
    * Display a listing of the resource.
    *
    * @return \Illuminate\Http\Response
    */
    public function index()
    {
        $todos = Todo::all();
        return response()->json([
            'status' => true,
            'todos' => $todos
        ]);
    }

    /**
    * Store a newly created resource in storage.
    *
    * @param \Illuminate\Http\Request $request
    * @return \Illuminate\Http\Response
    */
    public function store(Request $request)
    {
        $todo = Todo::create($request->all());
        return response()->json([
            'status' => true,
            'message' => "Todo Created successfully!",
            'todo' => $todo
        ], 200);
    }

    /**
    * Update the specified resource in storage.
    *
    * @param \Illuminate\Http\Request $request
    * @param \App\Models\Post $post
    * @return \Illuminate\Http\Response
    */
    public function update(Request $request, Todo $todo)
    {
        $todo->update($request->all());
        return response()->json([
            'status' => true,
            'message' => "Todo Updated successfully!",
            'todo' => $todo
        ], 200);
    }

    /**
    * Remove the specified resource from storage.
    *
    * @param \App\Models\Post $post
    * @return \Illuminate\Http\Response
    */
    public function destroy(Todo $todo)
    {
        $todo->delete();
        return response()->json([
        'status' => true,
        'message' => "Todo Deleted successfully!",
        ], 200);
    }
}
```
now create api route in `routes/api.php`  
```php
Route::apiResource('todos', TodoController::class);
```

And we can now test with Postman with our API  
https://www.postman.com/
