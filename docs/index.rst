django-referrer-policy |release|
================================

django-referrer-policy provides a middleware class implementing `the
Referrer-Policy header <https://www.w3.org/TR/referrer-policy/>`_ for
`Django <https://www.djangoproject.com/>`_-powered sites.

Setting the ``Referrer-Policy`` header allows you to control what, if
any, information is sent in the HTTP ``Referer`` header when a user
clicks a link on your site.


Installation
------------

django-referrer-policy supports Django 1.11 and Django 2.0, on Python
versions supported by those versions of Django:

* Django 1.11 supports Python 2.7, 3.4, 3.5, and 3.6.

* Django 2.0 supports Python 3.4, 3.5, and 3.6.

To install django-referrer-policy, run::

    pip install django-referrer-policy

This will use ``pip``, the standard Python package-installation
tool. If you are using a supported version of Python, your
installation of Python came with ``pip`` bundled, but if it is
missing, instructions are available for `how to obtain and install it
<https://pip.pypa.io/en/latest/installing.html>`_.

You can also obtain and install from a source-code checkout.

The development repository for django-referrer-policy is at
<https://github.com/ubernostrum/django-referrer-policy>. If you have
`git <http://git-scm.com/>`_ installed, you can obtain a copy of the
repository by typing::

    git clone https://github.com/ubernostrum/django-referrer-policy.git

From there, you can use normal git commands to check out the specific
revision you want, and install it using ``pip install -e .`` (the
``-e`` flag specifies an "editable" install, allowing you to change
code as you work on django-referrer-policy, and have your changes
picked up automatically).


Configuration
-------------

To use django-referrer-policy, you need to do two things. First, add
``django_referrer_policy.middleware.ReferrerPolicyMiddleware`` to your
Django ``MIDDLEWARE`` setting. Then, add the setting
``REFERRER_POLICY``, and set it to one of the acceptable values for
the ``Referrer-Policy`` header. The legal values are:

* ``'no-referrer'``
* ``'no-referrer-when-downgrade'``
* ``'origin'``
* ``'origin-when-cross-origin'``
* ``'same-origin'``
* ``'strict-origin'``
* ``'strict-origin-when-cross-origin'``
* ``'unsafe-url'``

For details of what these values mean, consult `the Referrer-Policy
header specification <https://www.w3.org/TR/referrer-policy/>`_.

Failing to set the ``REFERRER_POLICY`` setting, or setting it to an
invalid value, will cause the middleware to raise
``django.core.exceptions.ImproperlyConfigured``.


.. seealso::

  * `Mozilla Developer Network: Referrer-Policy
    <https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy>`_
  * `Security researcher Scott Helme explaining Referrer-Policy
    <https://scotthelme.co.uk/a-new-security-header-referrer-policy/>`_
