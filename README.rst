-----------------------
What is YUI Compressor?
-----------------------

`YUI Compressor <http://developer.yahoo.com/yui/compressor/>`_ is
a JavaScript and CSS minifier written in Java.
This package bundles the YUI Compressor JAR file to ease its use
in Python projects.
Note that **you still need to have Java Runtime Environment installed**.

For instance, you may use this package with ``buildout``.
First, create the ``buildout.cfg`` file::

    [buildout]
    parts = yuicompressor

    [yuicompressor]
    recipe = zc.recipe.egg
    eggs = yuicompressor

Next, download ``buildout`` bootstrap script and run the ``buildout``
itself::

    $ wget http://svn.zope.org/*checkout*/zc.buildout/trunk/bootstrap/bootstrap.py
    $ python bootstrap.py
    Creating directory 'bin'.
    Creating directory 'parts'.
    Creating directory 'develop-eggs'.
    Generated script 'bin/buildout'.
    $ bin/buildout
    Installing yuicompressor.
    Getting distribution for 'yuicompressor'.
    Got yuicompressor 2.4.6.
    Generated script 'bin/yuicompressor'.

The ``yuicompressor`` script is ready to use::

    $ bin/yuicompressor
    Usage: java -jar yuicompressor-x.y.z.jar [options] [input file]

    Global Options
    -h, --help                Displays this information
    --type <js|css>           Specifies the type of the input file
    --charset <charset>       Read the input file using <charset>
    --line-break <column>     Insert a line break after the specified column number
    -v, --verbose             Display informational messages and warnings
    -o <file>                 Place the output into <file>. Defaults to stdout.

    JavaScript Options
    --nomunge                 Minify only, do not obfuscate
    --preserve-semi           Preserve all semicolons
    --disable-optimizations   Disable all micro optimizations

    If no input file is specified, it defaults to stdin. In this case, the 'type'
    option is required. Otherwise, the 'type' option is required only if the input
    file extension is neither 'js' nor 'css'.


You could then integrate this with a package that relies on
the compressor, e.g. `django-compress`_ and worry no more.

.. _django-compress: http://code.google.com/p/django-compress/

User-level installation with ``easy_install`` does make sense
even for standalone use, e.g. having ``yuicompressor`` in your
``PATH``.


Versions
========

Version ``X.Y.Z`` of this package will bundle the corresponding
version of the compressor.
