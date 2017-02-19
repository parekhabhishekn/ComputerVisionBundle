Installation
============

Step 1: Download the Bundle
---------------------------

Open a command console, enter your project directory and execute the
following command to download the latest stable version of this bundle:

```console
$ composer require openwines/computer-vision-bundle "~1"
```

This command requires you to have Composer installed globally, as explained
in the [installation chapter](https://getcomposer.org/doc/00-intro.md)
of the Composer documentation.

Step 2: Enable the Bundle
-------------------------

Then, enable the bundle by adding it to the list of registered bundles
in the `app/AppKernel.php` file of your project:

```php
<?php
// app/AppKernel.php

// ...
class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = array(
            // ...

            new OpenWines\ComputerVisionBundle\OpenWinesComputerVisionBundle(),
        );

        // ...
    }

    // ...
}
```

Then create your API key: https://www.microsoft.com/cognitive-services/en-us/computer-vision-api

And copy it in `app/config/parameters.yml`:

```yaml
    parameters:
        (...)
        microsoft_computer_vision.api_token: myToken
```

Step 3: Test Usage
------------------

Perform an OCR on `vendor/openwines/computer-vision-bundle/src/OpenWines/ComputerVisionBundle/Resources/data/wines/`
and put the result in a `./wines.csv` file:

```console
php bin/console cv:ocr vendor/openwines/computer-vision-bundle/src/OpenWines/ComputerVisionBundle/Resources/data/wines/ fr -o ./wines.csv
cat wines.csv
```
