CultureObject v2.0.0
====================

Welcome
---------------------
CultureObject is an open source WordPress plugin designed to help you put your museum object records on the web. 


How it works
---------------------

* Install it from here (and shortly the WordPress plugin repository)
* Activate it
* Point it at your data
* Run the import
* Build the necessary theme pages to display your content. 
* Point in wonder at your beautiful new site before heading to the pub to celebrate.

At present the data you provide to CultureObject can be one of two flavours:

1. A publicly queryable RESTy API
2. A structured xml / json data file

The data "shape" - and how to deal with the data the plugin finds - is dealt with in what are called "providers". These are PHP classes which you'll find in the /providers directory.

The plugin is built to be extensible so that when other providers are added to this directory it'll pick them up in the interface and give you the option to select them and run the import.


Usage Instructions
---------------------
We use the master branch here for development. If you want a known working build, grab the latest tag. (Currently 1.1)

Originally an in-house project at [Thirty8Digital](http://www.thirty8.co.uk) by [Liam Gladdy](https://gladdy.uk)

We're currently building CultureObject into an expandable framework that will be listed in the WordPress plugin directory, and allow third-party plugins to add supply additional providers.

Presently, if you want to write a custom provider, you'll need to follow the default providers in the providers directory with the abstract class in CultureObject/Provider.class.php also giving you some pointers.

###A note of caution
If you're looking to go into a production environment in the near term, we'd recommend building against CultureObject 1.1, which we will continue to support until 2.0 is released.


Developers
---------------------
Version 2 adds support for image importing and field mapping. At the moment, only the CollectionSpace provider supports this functionality.

In order to enable field mapping, your theme must declare support for 'cos-remaps' using WordPress's [add_theme_support](http://codex.wordpress.org/Function_Reference/add_theme_support), from there you then use cos_get_remapped_field_name(<field_key>), or cos_remapped_field_name(<field_key>) to return, or output either the default, or remapped human-readable field name.