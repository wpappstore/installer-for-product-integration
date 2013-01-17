WP App Store Installer for Product Integration
==============================================

The following code is intended for developers to include in their themes/plugins to help distribute the WP App Store plugin and [earn affiliate revenue](http://wpappstore.com/affiliates/). The code adds a "WP App Store" item to the WordPress menu. When clicked, a page introduces WP App Store and allows the user to install the WP App Store plugin with one click.

![WP App Store Installer](http://cdn.wpappstore.com/asset/img/affiliates/installer2.png)

Integration
-----------

- Copy wp-app-store.php to your theme or plugin directory

- Paste the following code into your theme's functions.php or main plugin file

```php
if ( !class_exists( 'WP_App_Store_Installer' ) ) {
    require 'path/to/wp-app-store.php';
}

function my_wpasi_init() {
    if ( !is_admin() ) return;

	$affiliate_id = '5555555'; // Your affiliate ID
    
    global $my_installer; // Allows others to access the installer object
    $my_installer = new WP_App_Store_Installer( $affiliate_id );
}

add_action( 'init', 'my_wpasi_init' );
```

- Update `path/to/wp-app-store.php` to be the correct include path

- Update the affiliate ID with the one found in [your account](https://wpappstore.com/dashboard/). If you don't yet have an affiliate account, [sign up](http://wpappstore.com/affiliates/) for one instantly.

Customize the menu
------------------

By default, the installer adds a **Theme Store** submenu item under Appearance and
**Plugin Store** under Plugins. You can remove these and add your own menu item by 
using the `wpasi_admin_menu` hook.

The following example removes the default menus and adds an **App Store** submenu 
item under the Gravity Forms top level menu.

```php
function my_wpasi_menu_items( $menus ) {
	// Remove the default menu items
	unset( $menus['themes.php'] );
	unset( $menus['plugins.php'] );

	// Add a new menu item
	$menus['gf_edit_forms'] = array(
		'title' => 'App Store',
		'slug' => 'gf-wp-app-store-installer'
	);

	return $menus;
}

add_filter( 'wpasi_menu_items', 'my_wpasi_menu_items' );
```

Change Log
----------

### 0.4 (2013-01-16)
* Removed top level menu item in favor of submenu items
* Ability to override the default menu
* Moved initialization outside of the include file

### 0.3 (2012-10-17)
* Change "Hide Forever" to hide for all users

### 0.2.1 (2012-08-26)
* Bug fix: SSL warning in dashboard due to CSS file loaded over HTTP
* Better stats tracking

### 0.2 (2012-06-08)
* Added affiliate ID support

### 0.1.1 (2012-05-29)
* Detect WP App Store plugin by looking for WP\_App\_Store class (hat tip @alexkingorg)

### 0.1 (2012-04-24)
 * Initial release
