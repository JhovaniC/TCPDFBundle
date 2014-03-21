JhovaniCTCPDFBundle
=======================

This bundle facilitates easy use of the TCPDF PDF generation library in
Symfony2 applications.

It's based on the [WhiteOctoberTCPDFBundle][1], <- check that out!

Installation
------------

### Step 1: Add this to your composer.json
```
"require" : {
        "jhovanic/tcpdf-bundle": "dev-master"
    }
```

Now run the composer update to download the bundle and library:

```
$ php composer.phar update
```

### Step 2: Enable the bundle in the kernel

Add the bundle to the `registerBundles()` method in your kernel:

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new JhovaniC\TCPDFBundle\JhovaniCTCPDFBundle(),
    );
}
```

Using TCPDF
-----------

You can obtain the `jhovanic.tcpdf` service from the container,
and then create a new TCPDF object via the service:

``` php
$pdfObj = $container->get("jhovanic.tcpdf")->create();
```

From hereon in, you are using a TCPDF object to work with as normal.

Using a custom class
--------------------

If you want to use your own custom TCPDF-based class, you can use
the `class` parameter in your configuration eg in `config.yml`:

``` yaml
jhovanic_tcpdf:
    class: 'Acme\MyBundle\MyTCPDFClass'
```

The class must extend from the `TCPDF` class; an exception will be
thrown if this is not the case.

License
-------

This bundle is under the MIT license. See the complete license in the bundle:

    Resources/meta/LICENSE

[1]: https://github.com/whiteoctober/WhiteOctoberTCPDFBundle "WhiteOctoberTCPDFBundle"