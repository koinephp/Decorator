Koine Decorator
-----------------

Simple decorator base class for PHP.

[![Build Status](https://travis-ci.org/koine-php/koine-decorator.png?branch=master)](https://travis-ci.org/koine-php/koine-decorator)
[![Coverage Status](https://coveralls.io/repos/koine-php/koine-decorator/badge.png)](https://coveralls.io/r/koine-php/koine-decorator)
[![Code Climate](https://codeclimate.com/github/koine-php/koine-decorator.png)](https://codeclimate.com/github/koine-php/koine-decorator)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/koine-php/koine-decorator/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/koine-php/koine-decorator/?branch=master)
[![Latest Stable Version](https://poser.pugx.org/koine/koine-decorator/v/stable.svg)](https://packagist.org/packages/koine/koine-decorator)
[![Total Downloads](https://poser.pugx.org/koine/koine-decorator/downloads.svg)](https://packagist.org/packages/koine/koine-decorator)
[![Latest Unstable Version](https://poser.pugx.org/koine/koine-decorator/v/unstable.svg)](https://packagist.org/packages/koine/koine-decorator)
[![License](https://poser.pugx.org/koine/koine-decorator/license.svg)](https://packagist.org/packages/koine/koine-decorator)

### Usage

Create an class that extends Koine\Decorator and override only the 
changed methods in there.

```php
<?php
class Product
{
    public function getPrice()
    {
        return 123.99;
    }

    public function getName()
    {
        return "Product Name";
    }
}

class ProductDecorator extends \Koine\Decorator
{
    public function getPrice()
    {
        return 'US ' . $this->object->getPrice();
    }
}

$product   = new Product;
$decorator = new ProductDecorator($product);

$decorator->getName();  // Product Name
$decorator->getPrice(); // US 123.99
```

### Installing

#### Via Composer
Append the lib to your requirements key in your composer.json.

```javascript
{
    // composer.json
    // [..]
    require: {
        // append this line to your requirements
        "koine/decorator": "dev-master"
    }
}
```

### Alternative install
- Learn [composer](https://getcomposer.org). You should not be looking for an alternative install. It is worth the time. Trust me ;-)
- Follow [this set of instructions](#installing-via-composer)

### Issues/Features proposals

[Here](https://github.com/koine-php/decorator/issues) is the issue tracker.

### Contributing

Only TDD code will be accepted. Please follow the [PSR-2 code standard](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md).

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

### How to run the tests:

```bash
phpunit --configuration tests/phpunit.xml
```

### To check the code standard run:

```bash
phpcs --standard=PSR2 lib
phpcs --standard=PSR2 tests
```

### Lincense
[MIT](MIT-LICENSE)

### Authors

- [Marcelo Jacobus](https://github.com/mjacobus)
