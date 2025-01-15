1. install filament di laravel 
  -- composer require filament/filament:"^3.2" -W
 
  -- php artisan filament:install --panels

1. Install the Spatie Laravel Media Library package via Composer:

   ```bash
   composer require spatie/laravel-medialibrary:^10.0.0
   ```

2. Publish the package's configuration file:

   ```bash
   php artisan vendor:publish --provider="Spatie\MediaLibrary\MediaLibraryServiceProvider"
   ```

3. Run the migrations to create the necessary database tables:

   ```bash
   php artisan migrate
   ```

4. Add the `Spatie\MediaLibrary\HasMedia` trait to your model:

   ```php
   use Spatie\MediaLibrary\HasMedia;
   use Spatie\MediaLibrary\InteractsWithMedia;

   class YourModel extends Model implements HasMedia
   {
       use InteractsWithMedia;

       // Your model code here
   }
   ```

5. Use the `addMedia` method to upload files to your model:

   ```php
   $yourModel->addMedia($request->file('your_file_input'))
             ->toMediaCollection('your_collection_name');
   ```

6. Access your media files using the `getMedia` method:

   ```php
   $mediaItems = $yourModel->getMedia('your_collection_name');
   ```

These steps will help you install and configure the Spatie Laravel Media Library plugin for handling file uploads in your Laravel application.


