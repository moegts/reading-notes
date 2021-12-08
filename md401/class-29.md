# Django Custom User

## Django Custum User Model

always use a custom user model for all new Django projects.

**Setup**:

- create and navigate into a dedicated directory called `accounts` for our code
- install Django
- make a new Django project called `config`
- make a new app `accounts`
- start the local web server

Here are the commands to run:

`cd ~/Desktop`
`mkdir accounts && cd accounts`
`pipenv install django~=3.1.0`
`pipenv shell`
`django-admin.py startproject config .`
`python manage.py startapp accounts`
`python manage.py runserver`

**xxxxxxxxxxxxxxxxxxxxx**
Note that we did not run migrate to configure our database. It's important to wait until after we've created our new custom user model before doing so.
**xxxxxxxxxxxxxxxxxxxxx**

## AbstractUser vs AbstractBaseUser

`AbstractBaseUser` requires much, much more work. **have to read tutorial**

So we'll use `AbstractUser` which actually subclasses `AbstractBaseUser` but provides more default configuration.

### Custom User Model

Creating our initial custom user model requires four steps:

- update `config/settings.py`
- create a new `CustomUser` model
- create new `UserCreation` and `UserChangeForm`
- update the admin

In `settings.py` we'll add the `accounts` app and use the `AUTH_USER_MODEL` config to tell Django to use our new custom `user` model in place of the built-in User model. We'll call our custom user model `CustomUser`.

Within `INSTALLED_APPS` add `accounts` at the bottom. Then at the bottom of the entire file, add the `AUTH_USER_MODEL` config.

```py
# config/settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'accounts', # new
]
...
AUTH_USER_MODEL = 'accounts.CustomUser' # new
```

Now update accounts/models.py with a new User model which we'll call CustomUser.

```py
# accounts/models.py
from django.contrib.auth.models import AbstractUser
from django.db import models

class CustomUser(AbstractUser):
    pass
    # add additional fields in here

    def __str__(self):
        return self.username
```

We need new versions of two form methods that receive heavy use working with users. Stop the local server with `Control+c` and create a new file in the `accounts` app called `forms.py`.

```bash
(accounts) $ touch accounts/forms.py
```

We'll update it with the following code to largely subclass the existing forms.

```py

# accounts/forms.py
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm
from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ('username', 'email')

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ('username', 'email')

```

Finally we update admin.py since the Admin is highly coupled to the default User model.

```py
# accounts/admin.py
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ['email', 'username',]

admin.site.register(CustomUser, CustomUserAdmin)
```

And we're done! We can now run `makemigrations` and `migrate` for the first time to create a new database that uses the custom user model.

`python manage.py makemigrations accounts`

`python manage.py migrate`

### Superuser

`python manage.py createsuperuser`

**more steps**:

```py
# config/settings.py
TEMPLATES = [
    {
        ...
        'DIRS': [str(BASE_DIR.joinpath('templates'))], # new
        ...
    },
]
```

```py
# config/settings.py
LOGIN_REDIRECT_URL = 'home'
LOGOUT_REDIRECT_URL = 'home'
```

`mkdir templates`
`mkdir templates/registration`

Then create four templates:

`touch templates/registration/login.html`
`touch templates/registration/signup.html`
`touch templates/base.html`
`touch templates/home.html`

Update the files as follows:

```html
<!-- templates/base.html -->
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
</head>
<body>
  <main>
    
  </main>
</body>
</html>
```

```html
<!-- templates/home.html -->


  <p>You are not logged in</p>
```

```html

<!-- templates/registration/login.html -->


<h2>Log In</h2>
<form method="post">
  <button type="submit">Log In</button>
</form>

```

```html

<!-- templates//signup.html -->


<h2>Sign Up</h2>
<form method="post">
  <button type="submit">Sign Up</button>
</form>
```

Now for our urls.py files at the project and app level.

```py

# config/urls.py
from django.contrib import admin
from django.urls import path, include
from django.views.generic.base import TemplateView

urlpatterns = [
    path('', TemplateView.as_view(template_name='home.html'), name='home'),
    path('admin/', admin.site.urls),
    path('accounts/', include('accounts.urls')),
    path('accounts/', include('django.contrib.auth.urls')),
]
```

Create a `urls.py` file in the accounts `app`.

`touch accounts/urls.py`

Then fill in the following code:

```py
# accounts/urls.py
from django.urls import path
from .views import SignUpView

urlpatterns = [
    path('signup/', SignUpView.as_view(), name='signup'),
]
```

Last step is our views.py file in the accounts app which will contain our signup form.

```py
# accounts/views.py
from django.urls import reverse_lazy
from django.views.generic.edit import CreateView

from .forms import CustomUserCreationForm

class SignUpView(CreateView):
    form_class = CustomUserCreationForm
    success_url = reverse_lazy('login')
    template_name = 'registration/signup.html'
```

and here we go!!! congrat

Start up the server with `python manage.py runserver` and go to the homepage at `http://127.0.0.1:8000/`.
