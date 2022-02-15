ne_maas - Ubuntu Metal as a Service
=========

This role installs Ubuntu's Metal as a Service, via Snap. Honestly, the actual Metal as a Service implementation is buggy, despite being installed correctly, but this does bring up a functional instance. 

Requirements
------------

None

Role Variables
--------------

- **maas_version**: The current channel version of MaaS to deploy
  - Defaults to *3.1*
- **maas_admin_user**: The admin user to log into MaaS
  - Defaults to *maas_admin*
- **maas_admin_email**: The email for the admin user (not in use by Ubuntu's statements)
  - Defaults to *maas_admin@maas.example.com*
- **maas_github_id**: A Public Key to import from Github. If left blank, don't import a key
  - Defaults to *nothing*
- **maas_admin_password**: The password for the admin to log into the MaaS instance
  - Defaults to *abcd1234*
- **maas_var_location**: The place to store the Admin password, if randomly generated. Leave blank to not save
  - Defaults to */var/snap/maas/maas_admin_pw.txt*
- **maas_dns_forwarder**: The DNS forwarder for MaaS to use
  - Defaults to *1.1.1.1*
- **maas_region_name**: The name of the Region you would like MaaS to use
  - Defaults to *Local Region*

Note: Other variables exist in defaults, and can be safely overridden, but mostly are present for readability or idempotency's sake, so they don't really need to be messed with.

Dependencies
------------

No role dependencies.

Example Playbooks
----------------

```yaml
# Bare minimum deployment. Results in MaaS 3.1 at http://MY_IP_ADDRR:5240/MAAS, with a password written
# to /var/snap/maas/maas_admin_pw.txt
    - role: 'irontooch.homelab.ne_maas'
      vars:
        maas_admin_user: "maas_admin"
        maas_admin_password: "my_secret_password"
        maas_admin_email: "my_admin_email@gmail.com"
```

```yaml
# Like example 1, but override Region Name and DNS Forwarder to use other DNS
    - role: 'irontooch.homelab.ne_maas'
      vars:
      vars:
        maas_admin_user: "maas_admin"
        maas_admin_password: "my_secret_password"
        maas_admin_email: "my_admin_email@gmail.com"
        maas_region_name: "My Super Duper Region"
        maas_dns_forwarder: 8.8.8.8
```

License
-------

GPL v3.0

Author Information
------------------

Author is IronTooch
