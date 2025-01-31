# django-latch

![CI](https://github.com/javimoral/django-latch/workflows/CI/badge.svg)
[![codecov](https://codecov.io/gh/javimoral/django-latch/branch/master/graph/badge.svg)](https://codecov.io/gh/javimoral/django-latch)
[![Documentation Status](https://readthedocs.org/projects/django-latch/badge/?version=latest)](https://django-latch.readthedocs.io/en/latest/?badge=latest)

Django and Latch integration. Originaly developed by Javier Olascoaga and [RootedCON](http://rootedcon.com/).

# Requirements

- Python 3.4, 3.5, 3.6, 3.7, 3.8, 3.9, 3.10
- Django 2.0, 2.1, 2.2, 3.0, 3.1, 3.2, 4.0

## Installation

To install it, simply run:

    $ pip install django-latch

Or, if you prefer installing from source:

    $ git clone https://github.com/javimoral/django-latch.git
    $ cd django-latch
    $ python setup.py install

# Configuration

In your `settings.py` file you need to add the following directives:

```python
   INSTALLED_APPS = (
       [...]
        'latch',
    )

    # Append Latch Auth Backend the first in list
    AUTHENTICATION_BACKENDS = [
        'latch.auth_backend.LatchAuthBackend',
        [...]
    ]

    LATCH_APP_ID = <APP Id> # You can use os.environ if you prefer
    LATCH_APP_SECRET = <APP Secret>
    LATCH_BYPASS_WHEN_UNREACHABLE = True # True is the default behaviour. Configure as you need.
```

Configure app urls

```python
    from django.urls import path, include

    urlpatterns = [
        [...]
        path('latch/', include('latch.urls'))
        [...]
    ]
```

Then apply migrations

    $ python manage.py makemigrations

For more information, please refer to [documentation](https://django-latch.readthedocs.io).

# Bugs and requests

Please report any bug/issue or feature request in GitHub issue tracker.

https://github.com/javimoral/django-latch/issues

# License

This module is published under Apache 2.0 license. See LICENSE file for details.

`latch-sdk-python` is published under GNU General Public License 2.0. Rights belongs to ElevenPaths, more information and the updated version at:
https://github.com/ElevenPaths/latch-sdk-python

# Authors

Originaly developed by Javier Olascoaga and [RootedCON](http://rootedcon.com/).
