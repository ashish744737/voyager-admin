# Admin Panel in laravel 7 (voyager admin panel)
Please follow the following steps to integrate voyager admin panel in laravel 7.
1. Create project in laravel : 
    composer create-project laravel/laravel voyager-admin
2. Set up project :
    copy ".htaccess" file from "public folder" to "root directory" and rename "server.php" to "index.php" (which is in root directory).
3. Go to ".env" file and change APP_URL = http://localhost:8000/voyager-admin  (or as per your localhost server).
4. Install voyager package in your project :
    composer require tcg/voyager
5. Create database in your localhost phpmyadmin. (e.g.  voyager_panel)
6. set up database configuration in .env file
    DB_HOST=localhost
    DB_DATABASE=(your database name)
    DB_USERNAME=(database user)
    DB_PASSWORD=(database password)
Example
    DB_HOST=localhost
    DB_DATABASE=voyager_panel
    DB_USERNAME=root
    DB_PASSWORD=
7. Install voyager without dummy data
    php artisan voyager:install
    
    or
    
   Install voyager with dummy data
    php artisan voyager:install --with-dummy

8. If you installed without dummy data use following codes
        - If you want to use existing user as admin use
                php artisan voyager:admin your@email.com
        - If you want to create new admin use
                php artisan voyager:admin your@email.com --create
                
9. If you installed voyager with dummy data use following creadentials
        link : http://localhost:8000/voyager-admin/admin/login     (localhost/your_project_name/admin/login)
        user : admin@admin.com
        password : password
10. IF you will face issues like you cant see any images on admin panel then
     Go to Config/Filesystem.php
     'disks' =>[
        'public' => [
            'driver' => 'local',
            'root' => storage_path('app/public'),
            'url' => env('APP_URL').'/storage',
            'visibility' => 'public',
        ],
      ],
       
       - Change 'url' => env('APP_URL').'/storage', to 'url' => env('APP_URL').'/public/storage',
       You will see images on admin panel
 11. Now enjoy your admin panel....
---------------------------------
 How to use current project 
---------------------------------
 1. Download / clone project 
        - go to xampp/htdocs 
        - open command promt or terminal and use command : git clone https://github.com/ashish744737/voyager-admin.git
 2. create ".env" file in root directory and copy ".env.example" content to .env
 3. Configure .env file for
        APP_URL=http://localhost:8000/voyager-admin
        DB_HOST=localhost
        DB_DATABASE=(database name)
        DB_USERNAME=(database username e.g root)
        DB_PASSWORD=(database password)
 4. Update composer by using following command
        composer update
 5. Generate APP_KEY by using following command
        php artisan key:generate
 6. install voyager with or without dummy data as discussed above. Here i am using dummy data but you can install without dummy data.
        php artisan voyager:install --with-dummy
 7. Use following creadentials and links to run program
        link : http://localhost:8000/voyager-admin
        user:admin@admin.com   
        password:password
 8. If you dont have storage link then create it by using following command
        php artisan storage:link
 9. Enjoy the project
-------------------------------------------------------------------------
Reference : https://voyager-docs.devdojo.com/getting-started/installation
-------------------------------------------------------------------------

If you face any problems you can contact me at : ashish.pasekar@gmail.com

Thanks
Ashish A Pasekar
        
        
    
    
    
