# DataTables Bundle for Symfony2

## Current Version

DataTables 1.9.4 + DataTables Plug-ins

## Installation

### Add bundle to your composer.json file

``` js
// composer.json

{
    "require": {
        // ...
        "pinano/datatables-bundle": "dev-master"
    }
}
```

### Or, if you prefer, choose a specific version

``` js
// composer.json

{
    "require": {
        // ...
        "pinano/datatables-bundle": "1.9.4.1"
    }
}
```

### Add bundle to your application kernel

``` php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Pinano\DataTablesBundle\PinanoDataTablesBundle(),
        // ...
    );
}
```

### Download the bundle using Composer

``` bash
$ php composer.phar update pinano/datatables-bundle
```

### Install assets

Given your server's public directory is named "web", install the public vendor resources

``` bash
$ php app/console assets:install web
```

Optionally, use the --symlink attribute to create links rather than copies of the resources

``` bash
$ php app/console assets:install --symlink web
```
## Usage

Once you have imported all the resources to the vendor folder, you can self-import the JS into your Symfony project as usual with:

``` twig
{# block js #}
{% block javascripts %}
    {% javascripts filter='cssrewrite' output='js/dataTables.js'
        ...
        '@PinanoDataTablesBundle/Resources/public/js/jquery.dataTables.js'
        '@PinanoDataTablesBundle/Resources/public/extras/TableTools/media/js/ZeroClipboard.js'
        '@PinanoDataTablesBundle/Resources/public/extras/TableTools/media/js/TableTools.js'
        ...
        %}
        <script src="{{ asset_url }}"></script>
    {% endjavascripts %}
{% endblock %}
```

And with the CSS as well using with:
``` twig

{# block css #}
{% block stylesheets %}
    {% stylesheets filter='cssrewrite' output='css/dataTables.css'
        ...
        'bundles/pinanodatatables/css/jquery.dataTables.css'
        ...
        %}
        <link rel="stylesheet" type="text/css" media="screen" href="{{ asset_url }}" />
    {% endstylesheets %}
{% endblock %}
```
Note: See https://github.com/kriswallsmith/assetic/issues/53 for known limitations of assetic with CSS referencing.

## Licenses

I do not own DataTables files at all, I'm just providing a Bundle package to easy-install them all. Refer to the source code of the included files from DataTables for license information.

## References

1. http://datatables.net/
2. http://www.sprymedia.co.uk/
3. http://symfony.com
