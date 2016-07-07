# [Permissions](http://goo.gl/rUxv47)
- [Permission Inheritance](http://goo.gl/i5gaZy)
    ```
    Groups Permissions
    0 : Deny
    1 : Allow

    Users Permissions
    -1 : Deny
     1 : Allow
     0 : Inherit

    Administrator Group
    {
        "name" : "Administrator",
        "permissions" : {
            "user.create" : 1,
            "user.delete" : 1,
            "user.view"   : 1,
            "user.update" : 1
        }
    }

    Moderator Group
    {
        "name" : "Moderator",
        "permissions" : {
            "user.create" : 0,
            "user.delete" : 0,
            "user.view"   : 1,
            "user.update" : 1
        }
    }

    User - John Rambo
    {
        "id" : 1,
        "first_name" : "John",
        "last_name" : "Rambo",
        "groups" : ["administrator"],
        "permissions" : null
    }

    User - Rocky Balboa
    {
        "id" : 2,
        "first_name" : "Rocky",
        "last_name" : "Balboa",
        "groups" : ["moderator"],
        "permissions" : {
            "user.update" : 0
        }
    }

    User - Bruce Wayne
    {
        "id" : 3,
        "first_name" : "Bruce",
        "last_name" : "Wayne",
        "groups" : ["administrator", "moderator"],
        "permissions" : {
            "user.delete" : -1,
            "user.create" : 1
        }
    }
    ```

