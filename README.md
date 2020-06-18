# multiple-databases-in-django
This is a short project for showing how we can use multiple databases in django3.0.


This project shows how to connect postgresql. 
This Project consosts of 3 db's (default, usersdb, customerdb) all in postgres and 3 apps (contenter, userchecking, customer). 
It consists of router.py file in contenter app which is used as a database routing file.

Steps:-

create the project and the app normally you create n django. Add all the apps in INSTALLED_APPS in settings.py file

Router and database configuration in settings.py file:-

DATABASE_ROUTERS = ['contenter.router.CheckerRouter'] # it consists the path where your router.py file reside.


DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'contentdb',
        'USER': 'postgres',
        'PASSWORD': 'admin1234',
        'HOST': 'localhost',
        'PORT': '5432'
    },
    'usersdb': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'usersdb',
        'USER': 'postgres',
        'PASSWORD': 'admin1234',
        'HOST': 'localhost',
        'PORT': '5432'
    },
    'customerdb': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'customerdb',
        'USER': 'postgres',
        'PASSWORD': 'admin1234',
        'HOST': 'localhost',
        'PORT': '5432'
    }

}


Note :- The above description is for settings.py file and the remaining you will find in the project. 
Just need to create router.py file and need to use app_label in your models for reference.
