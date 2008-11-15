Django Layout
=============

Intended as a nice default starting point for Django, including deployment server configs. Essentially replaces `django-admin.py startproject [THING]`.

Project Naming
--------------

Obviously the `.git` objects are included when checking out from GitHub, so you should copy the appropriate directories to somewhere Git-free (if you want):

    $ cp -R . ../mynewdjangoproject
    $ rm -rf ../mynewdjangoproject/.git

By default it comes named as `yoursite`, but you should obviously name it yourself:

    $ mv yoursite mydomain

Python Path
------------

`manage.py` automatically patches your sys.path to include files under `lib`, so you can feel free to put Python modules here:

    $ svn co http://.../mymodule.py lib/.
    # inside a Python file in your Django project
    import mymodule
    # just works!

This allows you to bundle your own library modules or external dependencies (dmigrations, simplejson etc.) with your project as required. It also means that a checkout to a plain Python system should Just Work™.