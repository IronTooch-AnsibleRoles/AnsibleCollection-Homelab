Role Name
=========

A role to deploy the Jirafeau File Sharing server

https://gitlab.com/mojo42/Jirafeau



Requirements
------------

No additional requirements

Role Variables
--------------

jirafeau_admin_pass:    (Defaults to abcd1234)
ssl_cert_location:      (Defaults to HTTP )
ssl_key_location:       (Defaults to HTTP )
proxy_ip_address:       (Defaults to nothing)
server_name:            (Defaults to ansible_host)
max_upload_size_mb:     (Defaults to no restrictions)

php_version:            (Defaults to 7.4)

Dependencies
------------

No Dependencies

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

MIT

Author Information
------------------

Author is IronTooch