Aid-BI Developer Documentation
==============================

This repository currently contains "everything": application, documentation,
generated outputs, scripts.

Overview of folders
-------------------

/app
	Default couchdb application space.
	
/doc
	Application space to make documentation available on couchdb
	Contains generated output from other tools to make that documentation
	available without having to install those tools.
	
/documentation
	Source folder of documentation: wireframes, schemas, and so on.
	
Getting started
===============

Have a CouchDB
--------------

Either install CouchDB on your own machine or use a service like iriscouch.com

Create a database for your work, for instance aid-bi

Get CouchApp
------------

Install CouchApp on your machine.

Edit couchapp.rc to point to one or more deployment environments.

If you run CouchDB on your own machine, this could be just this:

	{"env":{"default":{"db":"http:\/\/admin:password@127.0.0.1:5984\/aid-bi"}}}
	
Note: we use symlinks in each CouchApp application folder to re-use this
central configuration for all applications.

Install an application
----------------------

The default application in folder /app can be installed with CouchApp:

	cd app
	couchapp push
	cd ..
	
This will upload all design documents and assets in the app folder to your
instance of CouchDB. You should then be able to open that application via:

	http://127.0.0.1:5984/aid-bi/_design/app/index.html

Install the onine documentation
-------------------------------

To install the online documentation, use a similar approach:

	cd doc
	couchapp push
	cd ..
	
You should be able to open the available documentation via: 

	http://127.0.0.1:5984/aid-bi/_design/doc/index.html
