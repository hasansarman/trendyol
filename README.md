# Trendyol Client Lib

The easiest way for using Trendyol APIs in PHP

## Installation

This package can be installed via Composer:

```bash
composer require boolxy/trendyol
```

## Usage

### Product Service

#### Create your own products on Trendyol

```php
use BoolXY\Trendyol\Trendyol;
use BoolXY\Trendyol\Models\Product;

$results = Trendyol::create($user, $pass, $supplier_id)
    ->productService()
    ->addProduct(new Product($attributes))
    ->addProduct(new Product($attributes))
    // ...
    ->create();
```
or
```php
use BoolXY\Trendyol\Trendyol;
use BoolXY\Trendyol\Models\Product;
use BoolXY\Trendyol\Collections\ProductCollection;

$products = new ProductCollection();
$products->add(new Product());
$products->add(new Product());
// ...

$results = Trendyol::create($user, $pass, $supplier_id)
    ->productService()
    ->setProducts($products)
    ->create();
```

#### Get brands
```php
use BoolXY\Trendyol\Trendyol;

$results = Trendyol::create($user, $pass, $supplier_id)
    ->productService()
    ->getBrands();
```

#### Get brands by name
```php
use BoolXY\Trendyol\Trendyol;

$results = Trendyol::create($user, $pass, $supplier_id)
    ->productService()
    ->getBrandsByName("TRENDYOL");
```


With reviewing the tests, you can learn more...

## Testing

Copy phpunit.xml.dist as phpunit.xml and update it. After then you can start testing.

```bash
vendor/bin/phpunit
```

or

```bash
composer test
```

## Credits

- [Sezai Ozarslan](https://github.com/sezaiozarslan)