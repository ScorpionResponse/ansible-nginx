Ansible Role: nginx
======================

[![Build Status](https://travis-ci.org/ScorpionResponse/ansible-nginx.svg?branch=master)](https://travis-ci.org/ScorpionResponse/ansible-nginx)

Ansible role to install nginx.

Requirements
------------

None.

Role Variables
--------------

### Required
* `nginx_application_dir`: The directory of the project containing the 
  application.  Example: /var/www/django_app
* `nginx_server_name`: The hostname of the server.  Example: example.com

### Optional
* `nginx_config_dir`: The directory to be used for config info.  Default:
  /etc/nginx
* `nginx_log_dir`: The directory to store logs.  Default: /var/log/nginx
* `nginx_user_name`: The user account to run nginx under. Default:
  nginx
* `nginx_group_name`: The group to run nginx under. Default: nginx
* `nginx_worker_processes`: The number of workers to instantiate. Default: 2
* `nginx_static_files_expires`: Expires time for static files. Default: 10d.
* `nginx_hashed_static_files`: Whether static files are hashed. Default: False
* `nginx_hashed_static_files_expires`: Expiration for hashed static files.
  Default: max

Dependencies
------------

* The ScorpionResponse.supervisord role will be use to install supervisord and
  run nginx with that.
* The ScorpionResponse.gunicorn role will be used to run gunicorn.

Example Playbook
----------------

Example usage:

    - hosts: all
      roles:
         - { role: ScorpionResponse.nginx }

License
-------

BSD

Author Information
------------------

Github: https://github.com/ScorpionResponse
