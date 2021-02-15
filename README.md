# Flutterway Payment Gateway Package For PHP

An easy to use php package for flutterway payment gateway
The easiest way to make and accept payments from customers anywhere in the world.

## Installation
Install via composer RECOMMENDED 

```bash
composer require seunex17/flutterwave-php-payment-gateway
```

## Usage

Checkout page

```php
use Flutterwave\Transaction;

require_once "../src/Flutterwave.php";

$rave = new Transaction('YOUR-SEC-KEY', 'YOUR-PUBLIC-KEY');

/*
===========================================================
* Let collect payment information from customer
===========================================================
*/

$request = [
    'tx_ref' => time(), //* A unique transaction references
    'amount' => 500, //* Amount to be charged
    'currency' => 'NGN', //* Payment currency
    'payment_options' => 'card', //* Payment options
    'redirect_url' => 'http://localhost/repo/flutterwave/example/verify.php', //* Redirect url to check payment status
    'customer' => [
        'email' => 'user@mail.com', //* Customer email
        'name' => 'Zubdev', //* Customer name,
        'phone' => '' //* Customer phone number
    ],
    'meta' => [
        //* An array of an additional information
    ],
    'customizations' => [
        'title' => 'Paying for a sample product', //* Payment title
        'description' => 'sample', //* Payment description
        'logo' => '' //* Your website logo url
    ]
];


//* Send data to Flutterwave hosted checkout page
$rave->checkout($request);
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
