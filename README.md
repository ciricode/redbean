RedBeanPHP 5
============

[![Build Status](https://travis-ci.org/gabordemooij/redbean.svg?branch=master)](https://travis-ci.org/gabordemooij/redbean)

RedBeanPHP is an easy to use ORM tool for PHP.

* Automatically creates tables and columns as you go
* No configuration, just fire and forget
* No complicated package tools, no autoloaders, just ONE file

Installation
------------

```bash
composer require gingteam/redbean
```

Quick Example
-------------

How we store a book object with RedBeanPHP:
```php
use GingTeam\RedBean\Facade as R;

R::setup('sqlite:'.__DIR__.'/data.db');

$book = R::dispense('book');
$book->author = 'Santa Claus';
$book->title = 'Secrets of Christmas';
R::store($book);

$qb = R::createQueryBuilder();

$data = $qb->start()
    ->select('*')
    ->from('book')
    ->get();
```

Yep, it's that simple.

More information
----------------

For more information about RedBeanPHP please consult
the RedBeanPHP website:

https://www.redbeanphp.com/
