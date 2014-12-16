CRUX devpi Image
================

A Docker image based on [crux](https://index.docker.io/u/_/crux) that runs a [devpi](http://doc.devpi.net) server (*a PyPi Cache*).

Usage
-----

    $ docker run -d -p 3141:3141 crux/devpi

To mount your own local devpi cache directory:

    $ docker run -d -v /path/to/devpi:/var/lib/devpi crux/devpi

pip Usage
---------

Use a configuration similar to this in your `~/.pip/pip.conf`:

    [global]
    index-url = http://localhost:3141/root/pypi/+simple/

setuptools Usage
----------------

Use a configuration similar to this in your `~/.pydistutils.cfg`:

    [easy_install]
    index_url = http://localhost:3141/root/pypi/+simple/
