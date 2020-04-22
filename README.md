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
6. set up database configuration in .env file <br>
    DB_HOST=localhost<br>
    DB_DATABASE=(your database name)<br>
    DB_USERNAME=(database user)<br>
    DB_PASSWORD=(database password)<br>
Example<br>
    DB_HOST=localhost<br>
    DB_DATABASE=voyager_panel<br>
    DB_USERNAME=root<br>
    DB_PASSWORD=<br>
7. Install voyager without dummy data : 
    php artisan voyager:install
    
    or
    
   Install voyager with dummy data :
    php artisan voyager:install --with-dummy

8. If you installed without dummy data use following codes<br>
        - If you want to use existing user as admin use<br>
                php artisan voyager:admin your@email.com<br>
        - If you want to create new admin use<br>
                php artisan voyager:admin your@email.com --create<br>
                
9. If you installed voyager with dummy data use following creadentials<br>
        link : http://localhost:8000/voyager-admin/admin/login     (localhost/your_project_name/admin/login)<br>
        user : admin@admin.com<br>
        password : password<br>
10. IF you will face issues like you cant see any images on admin panel then<br>
     Go to Config/Filesystem.php<br>
     'disks' =>[<br>
        'public' => [<br>
            'driver' => 'local',<br>
            'root' => storage_path('app/public'),<br>
            'url' => env('APP_URL').'/storage',<br>
            'visibility' => 'public',<br>
        ],<br>
      ],<br>
       
       - Change 'url' => env('APP_URL').'/storage', to 'url' => env('APP_URL').'/public/storage',<br>
       You will see images on admin panel<br>
 11. Now enjoy your admin panel....
---------------------------------
 How to use current project 
---------------------------------
 1. Download / clone project <br>
        - go to xampp/htdocs <br>
        - open command promt or terminal and use command : git clone https://github.com/ashish744737/voyager-admin.git<br>
 2. create ".env" file in root directory and copy ".env.example" content to .env
 3. Configure .env file for<br>
        APP_URL=http://localhost:8000/voyager-admin<br>
        DB_HOST=localhost<br>
        DB_DATABASE=(database name)<br>
        DB_USERNAME=(database username e.g root)<br>
        DB_PASSWORD=(database password)<br>
 4. Update composer by using following command<br>
        composer update
 5. Generate APP_KEY by using following command<br>
        php artisan key:generate
 6. install voyager with or without dummy data as discussed above. Here i am using dummy data but you can install without dummy data.<br>
        php artisan voyager:install --with-dummy
 7. Use following creadentials and links to run program<br>
        link : http://localhost:8000/voyager-admin<br>
        user:admin@admin.com   <br>
        password:password<br>
 8. If you dont have storage link then create it by using following command<br>
        php artisan storage:link
 9. Enjoy the project<br>
<hr>
Reference : https://voyager-docs.devdojo.com/getting-started/installation
<hr>
Thanks<br>
Ashish A Pasekar<br>
ashish.pasekar@gmail.com<br>
        
        
    
    
    
