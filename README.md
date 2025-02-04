# laravel_tips

Git clone Laravel project by using the command 
- Clone project folder to any path/folder
- Example: git clone https://link_to_project laravelproj

Jump into a project folder and install Laravel by using composer
- cd laravelproj
- composer install

Copy .env.example file to .env file and change the database connection setting
- Example:
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=mywebappdb
DB_USERNAME=username
DB_PASSWORD=password

Generate an application key
- php artisan key:generate

Increase memory for php
- memory_limit= 1028MB

Migrate database and insert some default data
- php artisan migrate

Run composer to autoload file
- composer dump-autoload

Link public folder to apache httpdocs (run on command prompt)
- mklink /d C:\xampp\htdocs\laravelproj C:\Project\laravelproj\public

Change host file in “C:\Windows\System32\drivers\etc\hosts”
- add more under 127.0.0.1 localhost

Example:
# localhost name resolution is handled within DNS itself.
#	127.0.0.1       localhost
#	::1             localhost

127.0.0.1       laravelproj.localhost

Add this in httpd.conf. though some says there are security risks with this but couldn't find a way without this

<Directory />
    AllowOverride none
    Require all granted
</Directory>

Add VirtualHost in “C:\xampp\apache\conf\extra\httpd-vhosts.conf” 

Example:
<VirtualHost *:80>
    ServerName localhost
    DocumentRoot "C:/xampp/htdocs"
    <Directory "C:/xampp/htdocs">
        DirectoryIndex index.php
    </Directory>
</VirtualHost>

NameVirtualHost 127.0.0.1:80
<VirtualHost *:80>
	<Directory "C:/xampp/htdocs/mapintegrator">
		Options FollowSymLinks Indexes
		AllowOverride All
		Order deny,allow
		allow from All
	</Directory>
	ServerName mapintegrator.localhost
	ServerAlias mapintegrator.localhost
	DocumentRoot "C:/xampp/htdocs/mapintegrator" 
</VirtualHost>

Troubleshoot
- ADD PATH variable for php [C:\xampp\php] & slao check there is no other php path in PATH variable.
- restart xampp and browse localhost

composer upgrade --no-scripts
npm i windows-build-tools
