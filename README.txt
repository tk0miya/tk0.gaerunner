tk0.gaerunner
=============

`tk0.gaerunner` is python script launcher for `Google App Engine <http://code.google.com/appengine/>`_.
`tk0.gaerunner` is wrapping some APIs using remote API calls,
So launched scripts are able to manupilate resources on appengine environment.

::

   % gaerunner my_app_id scripts/data_import.py


Source code and issue tracker can be found
at `https://bitbucket.org/tk0miya/tk0.gaerunner <https://bitbucket.org/tk0miya/tk0.gaerunner>`_.

Setting up AppEngine
--------------------

Before executing `tk0.gaerunner`, you must set up development environments.
* AppEngine SDK (google_appengine_1.x.x.zip)
* Accept remote_api calls on your application

Setup AppEngine SDK
~~~~~~~~~~~~~~~~~~~ 

Install AppEngine SDK. Use `appfy.recipe.gae <http://pypi.python.org/pypi/appfy.recipe.gae>`_.

Accept remote_api_calls on your application
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 

you must set up your application to accept remote_api calls.
Add remote_api handler to your app.xml and deploy it to Appengine.

Example
^^^^^^^

::

  handlers:
  - url: /remote_api
    script: $PYTHON_LIB/google/appengine/ext/remote_api/handler.py
    login: admin

Setting up tk0.gaerunner using buildout
---------------------------------------

If you use buildout for setting up development environments,
add above parts to buildout.cfg.

::

  [gaerunner]
  recipe = zc.recipe.egg
  eggs =
      tk0.gaerunner
  extra-paths =
      parts/google_appengine
      app/lib
      app/distlib.zip
      app

History
=======

0.1.0 (2010-12-12)
------------------
* first release

