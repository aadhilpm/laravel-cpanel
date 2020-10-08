# How to Upload Laravel project on cPanel


Make a duplicate of existing project on Xamp (Lets Call as "sports"). Cross check the working of projects by running server using following command

cmd>
cd C:\xampp\htdocs\sports
```
php artisan serve 
```

If everything is working perfectly then export database file (http://localhost/phpmyadmin)

Open cPanel>
create a new database, database user and add user to database with all preivileges using Manage User Privileges

Then open cpanel phpmyadmin and import sql file

Open C:\xampp\htdocs\sports and edit .env file with localhost, database, user we created on cpanel


## Example of .env updation
```
APP_URL=
DB_CONNECTION=mysql
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=Sports
DB_USERNAME=sportsaadhilp
DB_PASSWORD=PPAPAPSPOdd  
```

open cmd> 
cd C:\xampp\htdocs\sports

#### Run following command one by one   (https://www.larashout.com/laravel-clear-cache)
```
> php artisan config:cache

> php artisan config:clear

> php artisan cache:clear

> php artisan cache:clear

> php artisan route:cache

> php artisan view:clear
```
Compress and zip our sports folder under C:\xampp\htdocs\

open cpanel File Manger>public_html
Upload zip file and extract the folder (Lets call the folder as sports)

Move all files under public folder (public_html/sports/public) to public_html

Edit index.php on public_html following manner
```*/

require __DIR__.'/sports/vendor/autoload.php';


$app = require_once __DIR__.'/sports/bootstrap/app.php';

/*
```
Check the website URL on browser. Hopefully website will work perfectly 
