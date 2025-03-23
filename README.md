A very minimal Laravel repro for the filament PHP bug https://github.com/filamentphp/filament/issues/14852

To test:
- composer install & npm install
- the sqlite DB is commited, so you can create an admin user, or use the default admin user admin@admin.org / pw: admin
- run `php artisan serve` & `npm run dev`
- go to localhost:8000/admin
- go to the list view of the User resource
- you'll see that "State call count" is equal to 3, while it should be 1

The relevant code is in `app/Filament/Resources/UserResource.php`