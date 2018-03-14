
# Stannp PHP SDK

Our APIs provide programmatic access to your Stannp Bulk Mailer account. Things like configuring campaigns, feeding data and triggering mail pieces to be dispatched can all be achieved using simple yet secure HTTP requests. This SDK aims to provide a way to easily integrate our API into your app

## Setup

best installed via composer

```bash
composer require stannp\stannpphp
```

The autoloader must be required
```php
require  'YOUR/PROJECT/ROOT/vendor/autoload.php';
```
The API key must either be passed as a parameter at the instantiation of the object or set as a constant within your application. This will not work without a valid API key

You can find your api key at the bottom of your [Stannp settings page](https://dash.stannp.com/settings).

#### Example:
```php
define("STANNP_API_KEY", "API_KEY_HERE");
or
$user = new User("API_KEY_HERE");
```


## Usage
As with the API the SDK is broken down into the separate components a complete list of these classes are:

```php
use Stannp\API\Campaigns;
use Stannp\API\Groups;
use Stannp\API\Letters;
use Stannp\API\Postcard;
use Stannp\API\Recipients;
use Stannp\API\Reporting;
use Stannp\API\User;
```

A complete list of methods can be found [~~here~~]().
More information regarding parameters and API options can be found [here](https://www.stannp.com/direct-mail-api)

#### Usage examples:
```php
use Stannp\API\Postcard;

$user = new User();
$user->getMe();
```
```php
use Stannp\API\Postcard

$postcard = new Postcard();
$postcard->sendPostcard(
	"A6",
	"https://www.stannp.com/assets/samples/a6-postcard-front.jpg",
	"Hello World",
	"Signature goes here",
	"Mr",
	"John",
	"Smith",
	"123 Fakestreet",
	"Address ln 2",
	"Cityshire",
	"AB12 3CD",
	 true,
	"GB"
);
```

#### Output

All output is in JSON format, to convert to a PHP object use `json_decode()`