# Syntara
* Packages
    - [Syntara](http://goo.gl/4kq0zH) - An admin system for Laravel 4, made for user management easier | [Document](http://goo.gl/qvWrzK) | [Custom Development](http://goo.gl/o3PeYB)
        - [Forum](http://goo.gl/SkvZpq) | Example: [home controller](http://pastebin.com/4jwD5R9x) | [routes](http://pastebin.com/nk0Y6rr5) | [home index ](http://pastebin.com/VEXZSi2Q)
        - [AdminLTE](http://goo.gl/gxX9P6) | [Demo](http://goo.gl/9DJppW)
* Goto app and update your composer.json require file with
    ```
    "minimum-stability": "stable",
	"require": {
		"cartalyst/sentry": "2.1.*",
		"mrjuliuss/syntara": "1.2.*",
		"jakubsacha/adminlte": "dev-master"
	}
    ```
* Goto app folder and hit composer
    ```
    composer update
    php artisan syntara:update
    ```
<a href="https://www.flickr.com/photos/31031464@N03/14932655246" title="2014-08-18 14_02_26-FreeCommander - DOS by Leo Nguyen, on Flickr"><img src="https://farm4.staticflickr.com/3846/14932655246_c09e7e1857_n.jpg" width="320" height="149" alt="2014-08-18 14_02_26-FreeCommander - DOS"></a>
* Goto app/config/database.php and configure your database
<a href="https://www.flickr.com/photos/31031464@N03/14768985440" title="2014-08-18 13_55_12-D__ProjectPHP_laravel_testcms_app_config_database.php (WCL, WCL_DevGuides, WCL_N by Leo Nguyen, on Flickr"><img src="https://farm4.staticflickr.com/3907/14768985440_db635648a4_n.jpg" width="320" height="201" alt="2014-08-18 13_55_12-D__ProjectPHP_laravel_testcms_app_config_database.php (WCL, WCL_DevGuides, WCL_N"></a>
* Goto app/config/app.php and add service providers
    ```
    'Cartalyst\Sentry\SentryServiceProvider',
	'Mrjuliuss\Syntara\SyntaraServiceProvider',
	'Jakubsacha\Adminlte\AdminlteServiceProvider',
    ```
<a href="https://www.flickr.com/photos/31031464@N03/14932681366" title="2014-08-18 14_04_20-D__ProjectPHP_laravel_test_app_config_app.php (WCL, WCL_DevGuides, WCL_NodeFW, t by Leo Nguyen, on Flickr"><img src="https://farm4.staticflickr.com/3867/14932681366_8ff4e4819d_n.jpg" width="311" height="320" alt="2014-08-18 14_04_20-D__ProjectPHP_laravel_test_app_config_app.php (WCL, WCL_DevGuides, WCL_NodeFW, t"></a>
* and add aliases
    ```
    'Sentry' 		 => 'Cartalyst\Sentry\Facades\Laravel\Sentry',
    ```
<a href="https://www.flickr.com/photos/31031464@N03/14955688665" title="2014-08-18 14_07_09-D__ProjectPHP_laravel_testcms_app_config_app.php (WCL, WCL_DevGuides, WCL_NodeFW by Leo Nguyen, on Flickr"><img src="https://farm6.staticflickr.com/5580/14955688665_fa87eedc0d_n.jpg" width="274" height="320" alt="2014-08-18 14_07_09-D__ProjectPHP_laravel_testcms_app_config_app.php (WCL, WCL_DevGuides, WCL_NodeFW"></a>
* Install
    ```
    php artisan syntara:install
    ```
<a href="https://www.flickr.com/photos/31031464@N03/14952636121" title="2014-08-18 14_11_51-FreeCommander - DOS by Leo Nguyen, on Flickr"><img src="https://farm6.staticflickr.com/5561/14952636121_5c50b0935c_n.jpg" width="320" height="159" alt="2014-08-18 14_11_51-FreeCommander - DOS"></a>
```
php artisan create:user [user] [email] [password] Admin
```
<a href="https://www.flickr.com/photos/31031464@N03/14769067500" title="2014-08-18 14_16_05-FreeCommander - DOS by Leo Nguyen, on Flickr"><img src="https://farm4.staticflickr.com/3846/14769067500_d962c50f28_n.jpg" width="320" height="21" alt="2014-08-18 14_16_05-FreeCommander - DOS"></a>
* Publish assets
    ```
    php artisan asset:publish mrjuliuss/syntara
    php artisan config:publish mrjuliuss/syntara
    ```
<a href="https://www.flickr.com/photos/31031464@N03/14955416522" title="2014-08-18 14_19_27-FreeCommander - DOS by Leo Nguyen, on Flickr"><img src="https://farm4.staticflickr.com/3895/14955416522_e2ff899fb2_n.jpg" width="320" height="31" alt="2014-08-18 14_19_27-FreeCommander - DOS"></a>

# Run
* Goto [http://localhost/laravel/testcms/public/dashboard/login](http://localhost/laravel/testcms/public/dashboard/login)
<a href="https://www.flickr.com/photos/31031464@N03/14769114520" title="2014-08-18 14_21_39-Login by Leo Nguyen, on Flickr"><img src="https://farm4.staticflickr.com/3888/14769114520_8ecb0cd44f_n.jpg" width="320" height="254" alt="2014-08-18 14_21_39-Login"></a>
* Type account then show the dashboard
<a href="https://www.flickr.com/photos/31031464@N03/14952682781" title="2014-08-18 14_23_43-Syntara - Dashboard by Leo Nguyen, on Flickr"><img src="https://farm6.staticflickr.com/5595/14952682781_d4683de22c_n.jpg" width="320" height="153" alt="2014-08-18 14_23_43-Syntara - Dashboard"></a>
* Goto Users
<a href="https://www.flickr.com/photos/31031464@N03/14955479622" title="2014-08-18 14_27_56-Syntara - Users list by Leo Nguyen, on Flickr"><img src="https://farm4.staticflickr.com/3841/14955479622_670e7d5c59_n.jpg" width="320" height="130" alt="2014-08-18 14_27_56-Syntara - Users list"></a>
<a href="https://www.flickr.com/photos/31031464@N03/14952717391" title="2014-08-18 14_28_24-Syntara - admin by Leo Nguyen, on Flickr"><img src="https://farm4.staticflickr.com/3847/14952717391_58a022f7a5_n.jpg" width="320" height="124" alt="2014-08-18 14_28_24-Syntara - admin"></a>
