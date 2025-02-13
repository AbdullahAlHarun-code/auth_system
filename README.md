# Django JWT Authentication API

## Overview
Let's build a reusable, plugin-based Django API for JWT authentication that is clean, efficient, secure, and easily extensible for multiple projects. This API will include:

- **JWT Authentication** (with Refresh Tokens)
- **User Management** (Registration, Login, Logout, Profile)
- **Role-Based Access Control (RBAC)**
- **Two-Factor Authentication (2FA)**
- **Email Verification**
- **Swagger API Documentation**
- **Plugin-Based Architecture** (Easily extendable)

## Getting Started

### Step 1: Django Project Setup

#### 1.1 Install Required Dependencies
Run the following command to install necessary dependencies:

```bash
pip install django djangorestframework djangorestframework-simplejwt drf-yasg django-cors-headers django-environ
```

#### 1.2 Create Django Project and App

```bash
django-admin startproject core
cd core
django-admin startapp authentication
```

#### 1.3 Configure Django Settings
Modify `core/settings.py` to include the necessary Django apps:

```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'rest_framework',
    'rest_framework_simplejwt',
    'drf_yasg',
    'corsheaders',
    'users',
]
```

### Step 2: Configure JWT Authentication
Add the following JWT settings in `core/settings.py`:

```python
from datetime import timedelta

SIMPLE_JWT = {
    'ACCESS_TOKEN_LIFETIME': timedelta(minutes=30),
    'REFRESH_TOKEN_LIFETIME': timedelta(days=1),
    'ROTATE_REFRESH_TOKENS': True,
    'BLACKLIST_AFTER_ROTATION': True,
    'ALGORITHM': 'HS256',
    'SIGNING_KEY': 'your-secret-key',
}

REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': (
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ),
}
```

### Next Steps
Follow the step-by-step guide to set up authentication, role-based access control, two-factor authentication, and other essential features.

Stay tuned for further steps! 🚀
