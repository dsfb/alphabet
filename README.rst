========
alphabet
========

[![PyPI](https://img.shields.io/pypi/v/alphabet.svg)](https://pypi.python.org/pypi/alphabet)

``alphabet`` is a Python string class enhancement.

Installation
------------

The easiest way to install the package is via ``pip``::

    $ pip3 install alphabet

Usage
-----

**Obfuscation**

.. code:: python

    from alphabet import alphabet

    key = "foobar"
    s = alphabet.alphabet("python")

    print(s)
    > python

    t = s.obfuscate(key)
    print(bytes(t, 'utf-8'))
    > b'\x16\x16\x1b\n\x0e\x1c'

    print(t.obfuscate(key))
    > python

**Identify a string**

.. code:: python

    from alphabet import alphabet
    
    alphabet('%!').identify()
    > 'PostScript document text'
    
    alphabet('import os').identify()
    > 'Python'
    
    alphabet('<div>foobar</div>').identify()
    > 'XML'
    
    alphabet('Привет').identify()
    > 'ru'