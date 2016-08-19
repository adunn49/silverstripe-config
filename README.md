# Config

The aim of this is to implement the SilverStripe config system in a way that can be
understood by many and to improve performance whilst keeping the powerful features.

## Manifesto

### Simplicity over Complexity

We will strive to simplyfy the code and document its features and concepts at every level 
making it easier for others to understand and contribute.

### Performance over Features

This package aims to improve on performance and where appropriate change, remove or
disable features which prevent a performant solution. We aim to promote better PHP
architecture through the prioritisation of performance over feature.

## Usage

```
<?php

require 'vendor/autoload.php';

use micmania1\config\Config;
use micmania1\config\Transformer\Yaml;
use Symfony\Component\Finder\Finder;

$finder = new Finder();
$finder->in(__DIR__ . '/config')
    ->files()
    ->name('/\.(yml|yaml)$/');
$yaml = new Yaml($finder, 10);

$config = new Config($yaml);
$merged = $config->transform();

var_dump($merged);
```

## Tests

```
./vendor/bin/phpunit
```

