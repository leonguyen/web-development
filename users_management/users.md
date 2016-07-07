# [Users](http://goo.gl/lTRhZZ)
- [Sentry::createUser()](http://goo.gl/xwSCH6) | [Example](http://goo.gl/mee7Nv) | [Exceptions](http://goo.gl/DroJDL)
```
// Create the user
$user = Sentry::createUser(array(
    'email'     => 'john.doe@example.com',
    'password'  => 'test',
    'activated' => true,
));
// Create the user
$user = Sentry::createUser(array(
    'email'       => 'john.doe@example.com',
    'password'    => 'test',
    'activated'   => true,
    'permissions' => array(
        'user.create' => -1,
        'user.delete' => -1,
        'user.view'   => 1,
        'user.update' => 1,
    ),
));
```
- [Sentry::register()](http://goo.gl/h2Uhpu) | [Example](http://goo.gl/AZbJeK) | [Exceptions](http://goo.gl/tFh7Zl)
```
// Let's register a user.
$user = Sentry::register(array(
    'email'    => 'john.doe@example.com',
    'password' => 'test',
));
// Let's get the activation code
$activationCode = $user->getActivationCode();
```
- [Update a User](http://goo.gl/FPl8Gh) | [Examples](http://goo.gl/XzHQ4t) | [Exceptions](http://goo.gl/iH1DmQ)
    ```
    // Update the user details
    $user->email = 'john.doe@example.com';
    $user->first_name = 'John';

    // Update the user
    if ($user->save())
    {
        // User information was updated
    }
    else
    {
        // User information was not updated
    }
    ```
    - Assign a new Group to a User
    ```
    // Assign the group to the user
    $user->addGroup($adminGroup)
    ```
    - Remove a Group from the User
    ```
    // Remove the group to the user
    $user->removeGroup($adminGroup)
    ```
    - Update the User details and assign a new Group
- [Delete a user](http://goo.gl/z1cz3r) | [Example](http://goo.gl/HiBRMm) | [Exceptions](http://goo.gl/p4vUI7)
```
// Delete the user
$user->delete();
```
- [Activating a User](http://goo.gl/66Zhjf) | [Example](http://goo.gl/kCdYkd) | [Exceptions](http://goo.gl/nny1Gy)
```
// Attempt to activate the user
if ($user->attemptActivation('8f1Z7wA4uVt7VemBpGSfaoI9mcjdEwtK8elCnQOb'))
{
    // User activation passed
}
else
{
    // User activation failed
}
```
- [Reset a User Password](http://goo.gl/24a3fv) | [Exceptions](http://goo.gl/BU1GnS)
    - [Step 1](http://goo.gl/xtSJg0)
    ```
    // Get the password reset code
    $resetCode = $user->getResetPasswordCode();
    ```
    - [Step 2](http://goo.gl/plOrXZ)
    ```
    // Check if the reset password code is valid
    if ($user->checkResetPasswordCode('8f1Z7wA4uVt7VemBpGSfaoI9mcjdEwtK8elCnQOb'))
    {
        // Attempt to reset the user password
        if ($user->attemptResetPassword('8f1Z7wA4uVt7VemBpGSfaoI9mcjdEwtK8elCnQOb', 'new_password'))
        {
            // Password reset passed
        }
        else
        {
            // Password reset failed
        }
    }
    else
    {
        // The provided password reset code is Invalid
    }
    ```
- [Finding Users](http://goo.gl/m4Nazj) | [Exceptions](http://goo.gl/UukT4Z)
    - [Get the Current Logged in User](http://goo.gl/38W7xN)
    ```
    // Get the current active/logged in user
    $user = Sentry::getUser();
    ```
    - [Find all the Users](http://goo.gl/TV6icq)
    ```
    $users = Sentry::findAllUsers();
    ```
    - [Find all the Users with access to a permissions(s)](http://goo.gl/taA8QH)
    ```
    // Feel free to pass a string for just one permission instead
    $users = Sentry::findAllUsersWithAccess(array('admin', 'other'));
    ```
    - [Find all the Users in a Group](http://goo.gl/g5c70w)
    ```
    $group = Sentry::findGroupByName('admin');
    $users = Sentry::findAllUsersInGroup($group);
    ```
    - [Find a User by their Credentials](http://goo.gl/xsTCKC)
    ```
    $user = Sentry::findUserByCredentials(array(
        'email'      => 'john.doe@example.com',
        'password'   => 'test',
        'first_name' => 'John',
    ));
    ```
    - [Find a User by their Id](http://goo.gl/9ee4wI)
    ```
    $user = Sentry::findUserById(1);
    ```
    - [Find a User by their Login Id](http://goo.gl/Z8hGHB)
    ```
    $user = Sentry::findUserByLogin('john.doe@example.com');
    ```
    - [Find a User by their Activation Code](http://goo.gl/XJ3Q0Y)
    ```
    $user = Sentry::findUserByActivationCode('8f1Z7wA4uVt7VemBpGSfaoI9mcjdEwtK8elCnQOb');
    ```
    - [Find a User by their Reset Password Code](http://goo.gl/bQfPtv)
    ```
    $user = Sentry::findUserByResetPasswordCode('8f1Z7wA4uVt7VemBpGSfaoI9mcjdEwtK8elCnQOb');
    ```
    - Helpers
        - [checkPassword()](http://goo.gl/zXoRDe)
        ```
        if($user->checkPassword('mypassword'))
        {
            echo 'Password matches.';
        }
        else
        {
            echo 'Password does not match.';
        }
        ```
        - [getGroups()](http://goo.gl/Z2uljJ)
        ```
        // Get the user groups
        $groups = $user->getGroups();
        ```
        - [getPermissions()](http://goo.gl/Ju9Fzd)
        ```
        // Get the group permissions
        $groupPermissions = $group->getPermissions();
        ```
        - [getMergedPermissions()](http://goo.gl/bzA6dG)
        ```
        // Get the user permissions
        $permissions = $user->getMergedPermissions();
        ```
        - [hasAccess($permission)](http://goo.gl/pDkNJl)
        ```
        // Check if the user has the 'admin' permission. Also,
        // multiple permissions may be used by passing an array
        if ($user->hasAccess('admin'))
        {
            // User has access to the given permission
        }
        else
        {
            // User does not have access to the given permission
        }
        ```
        - [hasAnyAccess($permissions)](http://goo.gl/f2gZOn)
        ```
        // Check if the user has the 'admin' and 'foo' permission.
        if ($user->hasAnyAccess(array('admin', 'foo')))
        {
            // User has access to one of the given permissions
        }
        else
        {
            // User does not have access to any of the given permissions
        }
        ```
        - [isActivated()](http://goo.gl/efNTBw)
        ```
        // Check if the user is activated or not
        if ($user->isActivated())
        {
            // User is Activated
        }
        else
        {
            // User is Not Activated
        }
        ```
        - [isSuperUser()](http://goo.gl/bVxxVd)
        ```
        // Check if this user is a super user
        if ($user->isSuperUser())
        {
            // User is a super user
        }
        else
        {
            // User is not a super user
        }
        ```
        - [inGroup($group)](http://goo.gl/drfzAQ)
        ```
        // Find the Administrator group
        $admin = Sentry::findGroupByName('Administrator');

        // Check if the user is in the administrator group
        if ($user->inGroup($admin))
        {
            // User is in Administrator group
        }
        else
        {
            // User is not in Administrator group
        }
        ```
