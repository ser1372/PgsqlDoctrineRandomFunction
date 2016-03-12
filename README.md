# PgsqlDoctrineRandomFunction

PostgreSQL RANDOM() function for Doctrine ORM

[![Latest Stable Version](https://poser.pugx.org/qbbr/pgsql-doctrine-random-function/v/stable)](https://packagist.org/packages/qbbr/pgsql-doctrine-random-function)
[![Total Downloads](https://poser.pugx.org/qbbr/pgsql-doctrine-random-function/downloads)](https://packagist.org/packages/qbbr/pgsql-doctrine-random-function)
[![License](https://poser.pugx.org/qbbr/pgsql-doctrine-random-function/license)](https://packagist.org/packages/qbbr/pgsql-doctrine-random-function)

## Installation

### Step 1: Download the package

```bash
$ composer require qbbr/pgsql-doctrine-random-function
```

### Step 2: Configuration

```yaml
# app/config/config.yml

doctrine:
    orm:
        # ...
        dql:
            numeric_functions:
                Random: Qbbr\PgsqlDoctrineRandomFunction\DQL\RandomFunction
```

## Usage

```php
$em = $this->getDoctrine()->getManager();

$result = $em->createQueryBuilder()
    ->select('e')
    ->from('AppBundle:Entity', 'e')
    ->orderBy('RANDOM()')
    ->setMaxResults(10)
    ->getQuery()
    ->getResult();
```
