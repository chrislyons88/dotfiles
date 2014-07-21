## new seed project
cdp
seed <app-name>
grunt serve
s -n .

shift+cmd+f meanseedstylus -> <app-name>
shift+cmd+f mean-seed-stylus -> <app-name>

bower.json
 - add in libs

     "angular": "1.2.11",
    "json3": "~3.2.6",
    "es5-shim": "~2.1.0",
    "jquery": "~2.0.3",
    "jquery.ui": "~1.10.4",
    "bootstrap-sass-official": "~3.1.1",
    "bootstrap-stylus": "~3.1.0",
    "font-awesome": "~4.0.3",
    "angular-resource": "1.2.11",
    "angular-cookies": "1.2.11",
    "angular-sanitize": "1.2.11",
    "angular-route": "1.2.11",
    "moment": "~2.5.1",
    "chosen": "~1.1.0",
    "parsleyjs": "~2.0.0",
    "switchery": "~0.5.1"




## kickstrap project

```bash
md schedlr && echo "public" > .gitignore
kickstrap new .

# ctrl c to exit

g init && g add . && g commit -m 'Initial'

s .
```

open and edit:

app.coffee
1. app name
2. title

_setting.coffee
1. comment unneeded stuff
2. setup firebase
3. add in libs

main.styl
1. set theme

layout.jade
1. remove ks stuff



## Set up ST3 backup from existing installation

#### Make your backup Folder.

```bash

mkdir ~/Dropbox/ST3/
cd ~/Library/Application\ Support/Sublime\ Text\ 3/

```

#### Move the files

```bash

mv Packages/ ~/Dropbox/ST3/
mv Installed\ Packages/ ~/Dropbox/ST3/

```

#### Make symlinks

```bash

ln -s ~/Dropbox/ST3/Packages/ Packages
ln -s ~/Dropbox/ST3/Installed\ Packages Installed\ Packages

```

## Setting up sublime on new system

```bash

cd ~/Library/Application\ Support/Sublime\ Text\ 3/

# Remove packages and settings
rm -rf Packages/ ~/Dropbox/ST3/
rm -rf Installed\ Packages/ ~/Dropbox/ST3/

# Make symlinks
ln -s ~/Dropbox/ST3/Installed\ Packages Installed\ Packages
ln -s ~/Dropbox/ST3/Packages/ Packages

```

### creating laravel project
```
composer create-project laravel/laravel your-project-name --prefer-dist
cd your-project-name
php artisan key:generate

chmod -R 0777 app/storage
find bootstrap -name 'start.php' -exec sed -i '' -e 's/datamaskin/localhost/g' {} \;

php artisan migrate:make create_users_table --table=users --create
```

php

public function up()
{
    Schema::create('users', function(Blueprint $table)
    {
        $table->increments('id');
        $table->string('username')->unique();
        $table->string('password');
        $table->timestamps();
    });
}

/php

```
cd app/database/seeds
ts UserTableSeeder.php
```

php

```
 
class UserTableSeeder extends Seeder {
 
    public function run()
    {
        DB::table('users')->delete();
 
        User::create(array(
            'username' => 'firstuser',
            'password' => Hash::make('first_password')
        ));
 
        User::create(array(
            'username' => 'seconduser',
            'password' => Hash::make('second_password')
        ));
    }
 
}

```

uncommet database seeder

```
php artisan migrate
```

edit timezone
create database