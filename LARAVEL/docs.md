## Project Structure

### app

### bootstrap

### config

### database

### public

### resources

### routes

### storage

### tests

### vendor

## Tips

- Directories are separated by `.` instead of `/` in laravel functions: asset(), @extends(), @include()
- `.blade.php` extension is omitted while including views/layouts

## Routes

- located in `routes/` directory
- routes are defined using `Route` class
- each route takes two parameters: `url` and `callback function`
- callback function returns response/views

```
Route::get('/', function(){
  return "Hello!";
})

Route::get('/home', function(){
  return view("home");
})
```

- url parameter

```
Route::get('/home/{id}', function($id){
  return "Home Page id: ".$id;
})
```

- using controller in route
- callback function is replaced with controller's method/function

```
Route::get('/home/{id}', 'controllerName@method')
```

## Controllers

- location: `app/Http/Controllers/`
- response to requests with appropriate actions
- controls every request and response
- for form validator:
  - `$this->validate(['filed'=>['validator1','validator2']])`
  - if success, continues the execution below
  - if failed, errors are saved in `$errors` variable(array)

## Models

- location: `app/`
- used to insert/read/update/delete database table/model
- available some functions
  - all(): select all rows from table/model
  - save(): insert row(s) to the table/model
  - find(): find specific row(s)
  - paginate(): returns records in limit. takes limit number as argument
      - provides `link()` method which returns pagination component
- models are named singular
- database tables are created with model's plural form

## DB migration

- location: `database/migrations/`
- creating database tables from artisan cmd into the DBMS
- update existing tables schemas

## Laravel functions

`@extends('templateName')`

- used to extend template/master layout
- points to `resources/views` directory by default
- templates can have sections defined where dynamic contents are rendered.

`@include('layoutName')`

- used to include static layouts
- points to `resources/views` directory by default

`@yield('sectionName')`

- used to define a section
- contents are rendered dynamically from other layouts/views
- paired with `@section()`

`@section()`

- access section defined by `@yield` and display contents in that section
- contents are included between `@section('sectionName)` and `@endsection`

`asset()`

- used access assets (css/img/js)
- point to `public/` directory

`view()`

- returns view
- points to `resources/views` directory

  ```
  return view('home')
  ```

`url()`

- used to redirect/navigate to actual url links/endpoints

```
// routes
...
Route::get('/home','HomeController@index');
...

// usage
url('/home')
```

`route()`

- refer to endpoint/route that has name defined

```
// routes
...
Route::get('/home','HomeController@index')->name('home');
...

// usage
route('home')
// passing with parameter from route
route('home', $id)
```

## Middleware

- bridge between request and response
- `php artisan make:middleware middlewareName`
- middleware should be registered in App\Http\Kernel.php in routeMiddleware
- middleware are used in Routes to make use of them