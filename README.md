ERROR: Laravel 5.4 on Heroku. Forbidden You don't have permission to access / on this server
To resolve this issue, simply add the following to the script section of your composer.json
-----------------------------
 "post-install-cmd": [
     "php artisan clear-compiled",
     "chmod -R 777 public/"
 ]
----------------------------------
OLUTION STEPS:

Clone your project to your PC: heroku git:clone -a your-app-name

Create a file name: Procfile

Then save following lin of code in this Procfile:  web: vendor/bin/heroku-php-apache2 public/

Deploy your project back to heroku using commed: $ git add . $ git commit -am "make it better" $ git push heroku master 

I hope now no problem run your Laravel App!
