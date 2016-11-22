Djanog uWsgi
============

Run Djano app in uWsgi container

Requirements
------------

Debian, Django app

Role Variables
--------------

- `app` - determines directory structure and process names;
- `uwsgi_ini_tpl` - path to `uwsgi.ini` template file to use, if unset, we're using
    reasonable default one defined within role: `templates/_default_uwsgi.ini.j2`
- `supervisor_conf_tpl` - path to supervisor configuration file, if unset we're using
    default defined within role: templates/_default_supervisor.conf.j2
- `uwsgi_host` - default: `127.0.0.1`
- `uwsgi_port` - default: `8000`
- `uwsgi_procnum` - default: 2
- `uwsgi_max_requsts` - default: 100
- `priority`  - priority to start the server; lower value means it'll start sooner and shutdown later; default: 10

Dependencies
------------

- `xkoralsky.django_supervisor`

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: django_uwsgi, uwsgi_port: 8001 }

License
-------

BSD
