Grano Refine Reconciliation Support
===================================

`grano <http://grano.cc/>`_ is a toolkit for building journalistic social
network analysis applications on the web. This package contains support for 
the `Refine Reconciliation and Suggestion API <https://github.com/OpenRefine/OpenRefine/wiki/Reconciliation-Service-API>`_.
The API can be used to match entities from grano through the user interface
of Google Refine and OpenRefine, and thus assist cleaning raw data.


Installation
------------

``grano-reconcile`` requires that you have installed and configured
`grano <http://grano.cc/>`_. Please refer to `grano's documentation <http://docs.grano.cc/>`_
for further instructions. Afterwards, install the ``grano-reconcile``
package (from PyPI or source) into the same virtual environment.

You will also need to configure the Postgres database to support text matching
by installing the ``fuzzystrmatch`` extension::

    CREATE EXTENSION IF NOT EXISTS fuzzystrmatch;


Web API
-------

The plugin will provide the full reconviliation API as specified by the 
OpenRefine wiki. A service endpoint is provided for each project, with 
under the following URL pattern::

    /api/1/projects/<slug>/_reconcile

Further endpoints (for auto-complete suggestion) are available and referenced
from the main endpoint.
