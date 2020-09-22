# Django Custom User Model

- Django ships with a built-in User model for authentication, however the official Django documentation highly recommends using a custom user model for new projects. The reason is if you want to make any changes to the User model down the road--for example adding a date of birth field--using a custom user model from the beginning makes this quite easy. But if you do not, updating the default User model in an existing Django project is very, very challenging.

- So always use a custom user model for all new Django projects. However the official documentation example is not actually what many Django experts recommend using. There is a far easier yet still powerful approach to starting off new Django projects with a custom user model which I'll demonstrate here.

---

### AbstractUser vs AbstractBaseUser
- There are two modern ways to create a custom user model in Django: AbstractUser and AbstractBaseUser. In both cases we can subclass them to extend existing functionality however AbstractBaseUser requires much, much more work. Seriously, don't mess with it unless you really know what you're doing. And if you did, you wouldn't be reading this tutorial, would you?

### Custom User Model
*Creating our initial custom user model requires four steps*

- update config/settings.py
- create a new CustomUser model
- create new UserCreation and UserChangeForm
* update the admin
*In settings.py we'll add the accounts app and use the AUTH_USER_MODEL config to tell Django to use our new custom user model in place of the built-in User model. We'll call our custom user model CustomUser*

### Superuser
- It's helpful to create a superuser that we can use to log in to the admin and test out log in/log out. On the command line type the following command and go through the prompts.
```
(accounts) $ python manage.py createsuperuser
```
### Templates/Views/URLs
- Our goal is a homepage with links to log in, log out, and sign up. Start by updating settings.py to use a project-level templates directory.

```
TEMPLATES = [
    {
        ...
        'DIRS': [str(BASE_DIR.joinpath('templates'))], # new
        ...
    },
]
```
*Then set the redirect links for log in and log out, which will both go to our home template. Add these two lines at the bottom of the file.*
```
LOGIN_REDIRECT_URL = 'home'
LOGOUT_REDIRECT_URL = 'home'
```