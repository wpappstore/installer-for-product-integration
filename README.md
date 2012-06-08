WP App Store Installer for Product Integration
==============================================

The following code is intended for developers to include in their themes/plugins to help distribute the WP App Store plugin. The code adds a WP App Store item to the WordPress menu. When clicked, a page introduces the WP App Store and allows the user to install the WP App Store plugin with one click.


How to Integrate with a Theme
-----------------------------

Simply include `wp-app-store.php` in the folder with your theme files. Then add `include 'wp-app-store.php';` to your theme's `functions.php` file. 

How to Integrate with a Plugin
------------------------------

Simply include `wp-app-store.php` in the folder with your plugin files. Then add `include 'wp-app-store.php';` to your main plugin file.

Change Log
----------

### 0.2 (2012-06-08)
* Added affiliate ID support

### 0.1.1 (2012-05-29)
* Detect WP App Store plugin by looking for WP\_App\_Store class (hat tip @alexkingorg)

### 0.1 (2012-04-24)
 * Initial release
