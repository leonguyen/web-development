# [Authenticate](http://goo.gl/y04No8)
- [Sentry::authenticate()](http://goo.gl/WjMtaO) | [Example](http://goo.gl/Ujxgl5) | [Exceptions](http://goo.gl/fJp3RG)
    ```
    // Login credentials
    $credentials = array(
        'email'    => 'john.doe@example.com',
        'password' => 'password',
    );

    // Authenticate the user
    $user = Sentry::authenticate($credentials, false);
    ```
- [Sentry::authenticateAndRemember()](http://goo.gl/mslBr8) | [Example](http://goo.gl/QADilg)
    ```
    Sentry::authenticateAndRemember($credentials);
    ```
- [Sentry::login()](http://goo.gl/BCIupi) | [Example](http://goo.gl/zdS1Zp) | [Exceptions](http://goo.gl/0t5qAd)
    ```
    // Log the user in
    Sentry::login($user, false);
    ```
- [Sentry::loginAndRemember()](http://goo.gl/DL1t2S) | [Example](http://goo.gl/EpE9hv)
    ```
    Sentry::loginAndRemember($user);
    ```
- [Sentry::logout()](http://goo.gl/1jEp7Y) | [Example](http://goo.gl/mFc2O3)
    ```
    Sentry::logout();
    ```
- [Sentry::check()](http://goo.gl/GfllPu) | [Example](http://goo.gl/PmYXbd)
    ```
    if ( ! Sentry::check())
    {
        // User is not logged in, or is not activated
    }
    else
    {
        // User is logged in
    }
    ```
