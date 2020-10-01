## DEPLOYMENT

1. Upload Laravel project into cPanel root directory
2. From project folder move `public` folder's contents to the cPanel's `public_html` folder
3. Edit `index.php` from `public_html` directory
4. Configure `.env` file
5. Change File Permissions for web server

   a. Change folder ownership to web server account `www-data`

   ```
   sudo chown -R www-data:www-data /path/to/your/project/vendor
   sudo chown -R www-data:www-data /path/to/your/project/storage
   sudo chgrp -R www-data storage bootstrap/cache
   sudo chmod -R ug+rwx storage bootstrap/cache
   ```

   b. Add computer user to server group `www-data`

   ```
   sudo usermod -a -G www-data userName
   ```
