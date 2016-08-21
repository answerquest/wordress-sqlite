# wordress-sqlite
Ready-to-deploy fork of wordpress 4.6 with SQLite Integration, just PHP, no SQL database needed


* Run the `php-sqlite-pdo-test.php` script from browser for a quick check on whether your server supports sqlite.
* Unzip `wordpress-sqlite.zip` to your folder/server location. 
* Place the contents of the extracted `wordpress-sqlite` folder to where you want to deploy your site (ex: `/public_html/` in your FTP server account)
* From your browser, navigate to your server / folder location, and follow the installation steps like in any normal wordpress installation. 
* It will start with language selection, and jump straight to setting the site's name and admin credentials, without bothering with any db connection.

### Compatibility with backup plugins
Tested with Updraft Backup.. 

In settings, for files backup, leave this option checked ON: `Any other directories found inside wp-content`. This will include the sqlite backup in the database.

Don't bother backing up the database.

Tested on my local server with the same path.. worked fine.

If your restored site is to be at a different URL path, then you might have a problem, though.


