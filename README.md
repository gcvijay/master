1. create folder with a JSDProject

2. creation of venv
      python -m venv test

3. activation of venv
      test\Scripts\activate

4. installing a django framework
      pip install django

5. creation of project
      django-admin startproject ecommerce
      we will get the project folder
      settings.py, urls.py
-----settings.py ---
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]
------urls.py-------

from django.contrib import admin
from django.urls import path

urlpatterns = [
    path('admin/', admin.site.urls),
]
6. change the server
      cd ecommerce

7. to run the server
      python manage.py runserver

8. creation of app
    python manage.py startapp instagram
    we will get the instagram folder
    ---instagram app ----
    ---------views.py---------
    from django.shortcuts import render

9. app connection to the project
    ----confuging a settings.py   file----
    INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'instagram'       # app name
]

10. creation of templates folder inside the app
    instagram--> New--> Directory
    Give the name of the folder as a  templates

11. configure the templates folder
    within templates folder create the html files

12. creation of html files in templates
    templates--> New --> select the HTML file

13. connection of html file to the views
    ----configure the views.py ---
    def welcome_page(request):
        return render(request, 'index.html')

14. connection of views.py to the urls.py
    ---configure the urls.py -----
    from django.contrib import admin
    from django.urls import path
    from instagram import views     # views connection to urls

urlpatterns = [
        path('admin/', admin.site.urls),
        path('', views.welcome_page, name="home_page"),
        path('vamsi', views.dashboard, name="second_page")
]
