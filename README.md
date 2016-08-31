# wordress-sqlite
Ready-to-deploy fork of wordpress 4.6 with SQLite Integration, just PHP, no SQL database needed


* Run the `php-sqlite-pdo-test.php` script from browser for a quick check on whether your server supports sqlite.
* Unzip `wordpress-sqlite.zip` to your folder/server location. 
* Place the contents of the extracted `wordpress-sqlite` folder to where you want to deploy your site (ex: `/public_html/` in your FTP server account)
* From your browser, navigate to your server / folder location, and follow the installation steps like in any normal wordpress installation. 
* It will start with language selection, and jump straight to setting the site's name and admin credentials, without bothering with any db connection.

### Moving the site to a new place
If your website is moved to another path or its URL path has changed for any reason, then in the root folder, open the wp-config.php in a text editor, and insert this line before the `/* That's all, stop editing! Happy blogging. */` comment:

`define('RELOCATE',true);`

... and from browser, go to the login page:

`http://<new path>/wp-login.php`

.. and login to your admin dashboard.

Go to `Settings > General` to confirm and save the new path (in both the site url and other option), and go once to `Settings > Permalinks` to set the permalinks structure (even if the same option is selected, press "Save.." as that irons out a lot of creases).

So the site will set its url internally to the new one. But this will not change the paths at other places in your site, like in links, images etc; recommended to install a find and replace or similar plugin to change the paths for the rest of the site.

Once fully moved, edit `wp-config.php` again and remove the line or set it to false. You can keep it that way too if you wish, but that's usually discouraged for becoming some security issue.

To know more about moving sites, and for other options (non-database-related) please see:
https://codex.wordpress.org/Changing_The_Site_URL


### Compatibility with backup plugins
Tested with Updraft Backup.. 

In settings, for files backup, leave this option checked ON: `Any other directories found inside wp-content`. This will include the sqlite backup in the database.

Don't bother backing up the database.

Tested on my local server with the same path.. worked fine.

If your restored site is to be at a different URL path, then you might have to work on changing paths as shared above.

