SQL API for carto.com
========================

[![Build Status](https://travis-ci.org/CartoDB/CartoDB-SQL-API.png?branch=master)](https://travis-ci.org/CartoDB/CartoDB-SQL-API)

Provides a node.js based API for running SQL queries against CartoDB.

* Users are authenticated over OAuth or via an API KEY.
* Authenticated requests to this API should always be made over SSL.


## Requirements

* Node 10.x
* npm 6.x
* PostgreSQL >= 10.0
* PostGIS >= 2.4
* CARTO Postgres Extension >= 0.24.1
* Redis >= 4
* GDAL `1.11.0` (bin utils). See [installing GDAL](http://trac.osgeo.org/gdal/wiki/DownloadingGdalBinaries)
* zip commandline tool.
* C++11 (to build internal dependencies if needed)


## Install dependencies

```sh
$ npm install
```

## Usage


Create and edit config/environments/<environment>.js from .js.example files.
You may find the ./configure script useful to make an edited copy for you,
see ```./configure --help``` for a list of supported switches.

Make sure redis is running and knows about active cartodb user.

Make sure your PostgreSQL server is running, is accessible on
the host and port specified in the <environment> file, has
a 'publicuser' role (or whatever you set ``db_pubuser`` configuration
directive to) and trusts user authentication from localhost
connections.

```sh
node app.js <environment>
```

Supported <environment> values are development, test, production

See doc/API.md for API documentation.
For examples of use, see under test/.


## Tests

Run with:

```sh
$ npm test
```

If any issue arise see test/README.md

Note that the environment should be set to ensure the default
PostgreSQL user is superuser (PGUSER=postgres make check).

Contributing
---

See [CONTRIBUTING.md](CONTRIBUTING.md).
