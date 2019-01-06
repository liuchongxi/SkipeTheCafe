Group Member:
Kelvin Lin(jyl49)
Jacky Liu(jacky-liu9)
Andrew (yya123)
Allen (qianyilun)
## Instructions
1. Make sure `php artisan` is working on your dev envrionment

2. (For Windows) run `php artisan migrate:fresh --seed` to clean the database, applies all migrations and then seeds the database
    * Related directories: 
        * `\database\migrations`
        * `\database\seeds`
        * `\database\factories`

3. You should be able to view orders from database in the homepage now


## Enviroment Setup (for Windows)
1. Use `Laravel Homestead`

2. In `Homestead.yaml`:
    ```yaml
    folders:
        - map: D:\PHPDevelop\laravel-apps
        to: /home/vagrant/Code
    sites:
        - map: skipthecafe.test
        to: /home/vagrant/Code/skip_the_cafe/public
    ```
    You can decide your own directory for folders

3. In host file
    ```
    192.168.10.10 skipthecafe.test
    ```

4. Under Homestead folder, run `vagrant up`

5. Open up browser, visit [skipthecafe.test](skipthecafe.test)


##Enviroment Setup (for Mac)

1. Run `composer install` in the project root, since the master branch does not automatically include all dependencies 

2. Use `Laravel Homestead`

3. In `Homestead.yaml`:

   ```yaml
   folders:
       - map: your path
       to: your path
   sites:
       - map: skipthecafe.test
       to: /home/vagrant/Code/skip-the-cafe/public
   ```

4. In host file `sudo nano /etc/hosts`

   ```
   192.168.10.10 skipthecafe.test
   ```

5. Start your Vagrant

6. Cd to skip-the-cafe root path

7. Check mysql `mysql -u homestead -p` and the password is `secret`

8. `show databases;` to check if you have `homestead` database

9. Create new file `nano .env` with copying the following

   ```APP_NAME=Laravel
   APP_ENV=local
   APP_KEY=base64:7WHAu9EA9aGkIOSz0gQlnTD6WjGORCTqLmhRVCk1+0A=
   APP_DEBUG=true
   APP_URL=http://localhost
   LOG_CHANNEL=stack
   DB_CONNECTION=mysql
   DB_HOST=192.168.10.10
   DB_PORT=3306
   DB_DATABASE=homestead
   DB_USERNAME=homestead
   DB_PASSWORD=secret
   
   BROADCAST_DRIVER=log
   CACHE_DRIVER=file
   QUEUE_CONNECTION=sync
   SESSION_DRIVER=file
   SESSION_LIFETIME=120
   
   REDIS_HOST=127.0.0.1
   REDIS_PASSWORD=null
   REDIS_PORT=6379
   
   MAIL_DRIVER=smtp
   MAIL_HOST=smtp.mailtrap.io
   MAIL_PORT=2525
   MAIL_USERNAME=null
   MAIL_PASSWORD=null
   MAIL_ENCRYPTION=null
   
   PUSHER_APP_ID=
   PUSHER_APP_KEY=
   PUSHER_APP_SECRET=
   PUSHER_APP_CLUSTER=mt1
   
   MIX_PUSHER_APP_KEY="{PUSHER_APP_KEY}"
   MIX_PUSHER_APP_CLUSTER="{PUSHER_APP_CLUSTER}"
   ```

10. Run `php artisan migrate:fresh --seed`

11. Under Homestead folder, run `vagrant up`

12. Start server `php artisan serve` 

13. Open up browser, visit [skipthecafe.test](skipthecafe.test)



