WP App Store Installer for Product Integration
==============================================

The following code is intended for developers to include in their themes/plugins to help distribute the WP App Store plugin and [earn affiliate revenue](http://wpappstore.com/affiliates/). The code adds a "WP App Store" item to the WordPress menu. When clicked, a page introduces WP App Store and allows the user to install the WP App Store plugin with one click.

![WP App Store Installer](http://cdn.wpappstore.com/asset/img/affiliates/installer.png)

Configuration
-------------

1. Sign up for an affiliate account (if you haven't already)
1. Copy your affiliate ID
1. Open `wp-app-store.php`
1. Paste your affiliate ID as value for the `$affiliate_id` variable

Integration
-----------

1. Copy wp-app-store.php to your theme or plugin directory
1. Follow the instructions above to configure your affiliate ID
1. Add `include "/path/to/wp-app-store.php"` to your theme's `functions.php` file or for a plugin, your primary plugin file

Change Log
----------

### 0.2 (2012-06-08)
* Added affiliate ID support

### 0.1.1 (2012-05-29)
* Detect WP App Store plugin by looking for WP\_App\_Store class (hat tip @alexkingorg)

### 0.1 (2012-04-24)
 * Initial release
