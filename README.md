

1. create project

2. run the project
// php artisan serve

3. Create Database
php artisan migrate
php artisan migrate:fresh


Update your /app/Providers/AppServiceProvider.php to contain:

use Illuminate\Support\Facades\Schema;

public function boot()
{
    Schema::defaultStringLength(191);
}


4. Create foldes and files 
resources/views

5. resources
    views
        admin 
            tasks
                create.blade.php (form)
                index.blade.php (table)
                show.balde.php (form)
                edit.blade.php (form)
    index.blade.php
    dashboard.blade.php
    welcome.blade.php

Suppose we need to display index page then 
we need to create route 

 6. routes
    web.php

    Route::get('/', function () {
    return view('index');
    });

    Route::rources('task', 'App\Http\Controllers\TaskController');


    7. Create Model, Migration and Controller
    // php artisan make:model Task --migration --controller --resource


    8. Now , to display tasks/index
    go to brower
    http://127.0.0.1:8000/task/ (TaskController ko index)

<!-- after type task route name in URL -->
     public function index()
    {
        return view('admin.tasks.index'); (tasks/ index page)
    }


10. add necessary attributes , tocken and others in create file

11. Add database fields in database/migration/tasks-table
12. and update model also

and migrate
// php artisan migrate:fresh

13. Now. Ready for CRUD
controller


