Heroku buildpack: Python, Numpy, and Scipy
====================================================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks)
for Python apps, powered by [pip](http://www.pip-installer.org/).

This custom buildpack currently supports only NumPy 1.8.1 and SciPy 0.14.0
installations.

Please open a GitHub issue for any problems encountered or feature requests. If you
are interested in seeing a write-up/tutorial for creating this custom
buildpack, please let me know in a GitHub issue.

Details
-------

This buildpack only supports:

- NumPy 1.8.1
- SciPy 0.14.0

This package will also install compiled runtime libraries for BLAS, LAPACK,
ATLAS, and Fortran, which are needed by NumPy and SciPy at runtime.

If you desire older NumPy or SciPy packages, please take a look at
https://github.com/dbrgn/heroku-buildpack-python-sklearn

Usage
-----
For a new app:

    heroku create --buildpack https://github.com/agilgur5/heroku-buildpack-scipy

For an existing app:

    heroku config:set BUILDPACK_URL=https://github.com/agilgur5/heroku-buildpack-scipy

Demo
----

    $ mkdir testheroku
    $ cd testheroku
    $ git init
    $ heroku create --buildpack https://github.com/agilgur5/heroku-buildpack-scipy
    $ echo -e "numpy==1.8.1\nscipy==0.14.0" > requirements.txt
    $ git add requirements.txt
    $ git commit -m 'Added requirements'
    $ git push heroku master


Acknowledgments
---------------

This fork is taken from @thenovices -- I owe thanks to him, @dbrgn, @wyn, and others for
setting up a lot of the code here.
