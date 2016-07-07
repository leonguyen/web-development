# Menu Management
* Packages
    - [Menu](http://goo.gl/rE43Nb) - Menu made easy
        - [Laravel Menu](http://goo.gl/8IenZ1) - A quick way to create menus in Laravel 4.x
        - [L4-Smarty-Menubuilder](http://goo.gl/BCvI2J)
        - [Laravel-Navigation](http://goo.gl/lWqoWQ)
        - [laravel-shop-menu](http://goo.gl/ITWDmD) -  Menu ordering/management application demo, like Wordpress menu manager
        - [delatbabel/nestedmenus](https://goo.gl/OSAerN) - Database storage of nested menus, including rendering
        - [spatie/laravel-menu](https://goo.gl/44BRj7) - Html menu generator for Laravel
        - Frontend
            - [Laravel 4](http://goo.gl/MXFQvM) - Simple Menus
            - [Menuizer](http://goo.gl/NDf282)
* References
    - [WordPress - Mega Menu Plugin](http://youtu.be/WOKrL1RP1lI)
    - [OctoberCMS - Menu Lists](http://goo.gl/Q8mtZc)
* JS Libraries
    - Tree
        - [Nestable](http://goo.gl/Af9LJu)
        - [jquery-tabledrag](http://goo.gl/YDJGHT) - This is a fork of the Drupal Tablesort component. It allows you to make tables sortable
        - [jquery-treetable-ajax-persist](http://goo.gl/tZyZc9) - Extensions over jQuery treetable that supports ajax and persistence of branch expand statuses
        - [TreeGrid jQuery plugin](http://goo.gl/50Sfgt) - TreeGrid from HTML table
    - Menus
        - [metisMenu](http://goo.gl/8mPIU5) | Demo - Easy menu jQuery plugin for Twitter Bootstrap 3
        - [FlexNav](http://goo.gl/i8oWO4) - A jQuery plugin for responsive menus
        - [slimMenu](http://goo.gl/HudLXC) - slimMenu is a lightweight jQuery plugin, which is made to create responsive and multi-level navigation menus on the fly
        - [jQuery ReSmenu](http://codeb.it/resmenu/) - jQuery ReSmenu is a very simple and lightweight (~1Kb) jQuery plugin that collapse ul menus into select on responsive layouts
        - [jQuery contextMenu](http://goo.gl/uSMnNL)
        - [Lava Lamp](http://goo.gl/s41yz7)
        - [jQuery LavaLamp Plugin](http://goo.gl/mmKnX6)
* Tutorial
    - Storing Hierarchical Data in a Database [Part 1](http://goo.gl/sKxapD) | [Part 2](http://goo.gl/qqNqGA) | [Part 3](http://goo.gl/VNqqog)
* Schema
```
| Name       | Type      | Desc           | Note |
| --         | --        | --             | --   |
| id         | INT       | Page Id        | PK   |
| parent_id  | INT       | Parent Page Id | Idx  |
| lft        | INT       | Left           | Idx  |
| rgt        | INT       | Right          | Idx  |
| depth      | INT       | Depth          |      |
| created_at | TIMESTAMP | Created Time   |      |
| updated_at | TIMESTAMP | Updated Time   |      |
php artisan generate:scaffold page --fields="parent_id:integer, lft:integer, rgt: integer, depth: integer"
```
