# Throttle
- [Disable the Throttling Feature](http://goo.gl/UITbFf)
    ```
    // Get the Throttle Provider
    $throttleProvider = Sentry::getThrottleProvider();

    // Disable the Throttling Feature
    $throttleProvider->disable();
    ```
- [Enable the Throttling Feature](http://goo.gl/4xBoQ3)
    ```
    // Get the Throttle Provider
    $throttleProvider = Sentry::getThrottleProvider();

    // Enable the Throttling Feature
    $throttleProvider->enable();
    ```
- [Check the Throttling Feature Status](http://goo.gl/BBEM99)
    ```
    // Check if the Throttling feature is enabled or disabled
    if($provider->isEnabled())
    {
        // The Throttling Feature is Enabled
    }
    else
    {
        // The Throttling Feature is Disabled
    }
    ```
- [User Throttling](http://goo.gl/WV20Jm) | [Exceptions](http://goo.gl/9EYlPm)
    - [Ban user(s)](http://goo.gl/kYIjro)
    ```
    // Find the user using the user id
    $throttle = Sentry::findThrottlerByUserId(1);

    // Ban the user
    $throttle->ban();
    ```
    - [Unban user(s)](http://goo.gl/iPJcIo)
    ```
    // Find the user using the user id
    $throttle = Sentry::findThrottlerByUserId(1);

    // Unban the user
    $throttle->unBan();
    ```
    - [Check if a User is Banned](http://goo.gl/9XfWRS)
    ```
    if($banned = $throttle->isBanned())
    {
        // User is Banned
    }
    else
    {
        // User is not Banned
    }
    ```
    - [Suspend user(s)](http://goo.gl/nAr81x)
    ```
    // Suspend the user
    $throttle->suspend();
    ```
    - [Unsuspend user(s)](http://goo.gl/M73vgm)
    ```
    // Unsuspend the user
    $throttle->unsuspend();
    ```
    - [Check if a User is Suspended](http://goo.gl/rHVV1r)
    ```
    if($suspended = $throttle->isSuspended())
    {
        // User is Suspended
    }
    else
    {
        // User is not Suspended
    }
    ```
    - [Set the User Suspension Time](http://goo.gl/BWlsQn)
    ```
    $throttle->setSuspensionTime(10);
    ```
    - [Get the User Suspension Time](http://goo.gl/kFYCMG)
    ```
    $suspensionTime = $throttle->getSuspensionTime();
    ```
    - [Add a Login Attempt](http://goo.gl/mxZstj)
    ```
    $throttle->addLoginAttempt();
    ```
    - [Get Login Attempts](http://goo.gl/8Mctoa)
    ```
    $attempts = $throttle->getLoginAttempts();
    ```
    - [Clear Login Attempts](http://goo.gl/YbO7Ic)
    ```
    $throttle->clearLoginAttempts();
    ```
    - [Check the User Throttle Status](http://goo.gl/RLQ6rL)
    ```
    if ($throttle->check())
    {
        echo 'Good to go.';
    }
    ```
    - [Set Attempt Limit](http://goo.gl/aJJLyT)
    ```
    $throttle->setAttemptLimit(3);
    ```
    - [Get Attempt Limit](http://goo.gl/go9Tni)
    ```
    $attemptLimit = $throttle->getAttemptLimit();
    ```
- [Find User(s)](http://goo.gl/Yc5ACy) | [Exceptions](http://goo.gl/Z7Xkv6)
    - [Find a User by their Id](http://goo.gl/t9FYHW)
    ```
    $throttle = Sentry::findThrottlerByUserId(1);
    ```
    - [Find a User by their Login](http://goo.gl/7xmnCM)
    ```
    $throttle = Sentry::findThrottlerByUserLogin('john.doe@example.com');
    ```
