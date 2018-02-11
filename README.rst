.. -*-restructuredtext-*-

.. image:: https://travis-ci.org/ubernostrum/django-referrer-policy.svg?branch=master
    :target: https://travis-ci.org/ubernostrum/django-referrer-policy

django-referrer-policy provides a middleware class implementing `the
Referrer-Policy header <https://www.w3.org/TR/referrer-policy/>`_ for
`Django <https://www.djangoproject.com/>`_-powered sites.

Setting the ``Referrer-Policy`` header allows you to control what, if
any, information is sent in the HTTP ``Referer`` header when a user
clicks a link on your site.

Documentation is `available online
<https://django-referrer-policy.readthedocs.io/>`_.
