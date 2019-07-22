Yii2 behavior for date fields processing
========================================

The Behavior class for operations with date fields in Russian format.

No more maintained, please use [sergmoro1\yii2-ru-kit](https://github.com/sergmoro1/yii2-ru-kit).

Installation
------------

```php
$ composer require sergmoro1/yii2-ru-date "dev-master"
```

Usage
-----

You should define behavior in a Model class.

```php
use sergmoro1\rudate\RuDate;

class Post extends ActiveRecord
{
  public function behaviors() {
    return [
      'RuDate' => ['class' => RuDate::className()]
    ];
  }
```

And use it in appropriate place in a view.

```php
<?= $model->getFullDate('created_at'); ?>
```

Only month and year.

```php
<?= $model->getFullDate('created_at', 'M Y'); ?> // Фев 2018
```

Full month, day and year.

```php
<?= $model->getFullDate('created_at', 'F d из t, Y (e)'); ?> // Февраль 13 из 28, 2018 (UTC)
```
