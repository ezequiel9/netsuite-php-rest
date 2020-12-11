# Netsuite PHP - Wrapper Rest

This is a package that wraps Netsuite API Rest.

## Installation

Just add it to vendor folder [via composer require](https://getcomposer.org/).

```bash
composer require ezequiel9/netsuite-php-rest # Not live yet, sorry! 
```

## Configuration

```php
# Define constants
const NETSUITE_ACCOUNT_ID;
const NETSUITE_OAUTH2_CLIENT_ID;
const NETSUITE_OAUTH2_CLIENT_SECRET;
const NETSUITE_OAUTH2_CALLBACK_URL;
const NETSUITE_TOKEN_ID;
const NETSUITE_TOKEN_SECRET;


# instance the code oauth2 listner
use Ezequiel9/Netsuite;

new NetsuiteCodeListener();


```



## Usage

```php
use Ezequiel9/Netsuite;

$netsuite = new Wrapper();

$page = 1;

# Get all customers
$customers = $netsuite->getCustomers();

# Get all customers with pagination
$customers = $netsuite->getCustomers($page);

# Get all Items
$items = $netsuite->getItems();

# Get single item -> fields expanded
$item = $netsuite->getItem($netsuiteItemID);

...easy enough right? :)

```

## Available Methods

```php
# Customers
$netsuite->getCustomer($netsuiteCustomerID);
$netsuite->getCustomerByEmail($email);
$netsuite->getCustomers($pageNumber); // max 1000 per page
$netsuite->createCustomer($arrayData); // Structure in docs
$netsuite->updateCustomer($arrayData); // Structure in docs
$netsuite->deleteCustomer($netsuiteCustomerID);

$netsuite->getItem($netsuiteItemID);
$netsuite->getItems($page);

$netsuite->getSalesOrder($netsuiteSalesOrderID);
$netsuite->createSalesOrder($arrayData); // Structure in docs
$netsuite->updateSalesOrder($arrayData); // Structure in docs
$netsuite->deleteSalesOrder($netsuiteSalesOrderID);

$netsuite->getInvoice($netsuiteTransactionID);
$netsuite->getInvoices($page);

# more coming....

```


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
