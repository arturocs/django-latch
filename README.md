# django-latch

[![Build Status](https://travis-ci.com/javimoral/django-latch.svg?branch=master)](https://travis-ci.com/javimoral/django-latch)
[![codecov](https://codecov.io/gh/javimoral/django-latch/branch/master/graph/badge.svg)](https://codecov.io/gh/javimoral/django-latch)

Django and Latch integration

# Requirements

- Python > 3.5
- Django >= 2.0

## Installation

To install it, simply:
   
    $ git clone https://github.com/javimoral/django-latch.git
    $ cd django-latch
    $ python setup.py install


# Configuration

In your ``settings.py`` file you need to add the following directives:

```python

   INSTALLED_APPS = (
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'latch',
    )

    # Add auth profile 
    AUTH_PROFILE_MODULE='latch.UserProfile'
    
    # Add the authentication backend
    AUTHENTICATION_BACKENDS = (
            'latch.auth_backend.LatchAuthBackend',
    )
```

We create some models in database, so you must apply migrations after installing the app.

    $ python manage.py makemigrations

Like `django.contrib.auth` we extend Django Admin templates, if you want to your design, override the following templates:

    latch
    └── templates
        ├── latch_message.html
        ├── latch_pair.html
        ├── latch_status.html
        └── latch_unpair.html

# TODO

* Add a signal when deleting a user to remove the profile
* Add the UserProfile management to the admin
* Add 2FA support


# Bugs and requests

Please report any bug/issue or feature request in GitHub's issue tracker.

https://github.com/javimoral/django-latch/issues


# License

You can use this module under Apache 2.0 license. See LICENSE file for details.

latch-sdk-python is published under GNU General Public License 2.0. Rights belongs to ElevenPaths, more information and updated versionas at:
https://github.com/ElevenPaths/latch-sdk-python

# Author

Originaly developed by Javier Olascoaga and RootedCON

