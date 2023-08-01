See Documentation here - https://aamarpay.readme.io/reference/initiate-payment-json

# CSRF Token Error / 419

In Laravel, you can handle CSRF Token Errors (status code 419) by customizing the "VerifyCsrfToken middleware", which is located in the "app/Http/Middleware/VerifyCsrfToken.php" file. To address this error, you need to declare the success, fail, and cancel URLs/routes in the middleware.

    use Illuminate\Foundation\Http\Middleware\VerifyCsrfToken as Middleware;
    class VerifyCsrfToken extends Middleware
    {
        protected $except_urls =  
        'your/success_url',
            'your/fail_url',
            'your/cancel_url',
        ];
       
    }


# Session Log Out Error in Laravel

The error is related to the 'same_site' and 'secure' options in the 'session.php' configuration file.

file path = "app\Http\Middleware\session.php"

Change 'secure' => env('SESSION_SECURE_COOKIE'), to 'secure' => true;<br>
Change 'same_site' => 'lax', to 'same_site' => 'none';
