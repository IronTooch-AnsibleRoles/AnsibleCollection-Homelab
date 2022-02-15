Bitwarden
=========

Installs Bitwarden on a bare-metal server. Configures for self-hosting with a Smallstep Certificate Authority (Another role within the collection)

Requirements
------------

None

Role Variables
--------------

- **service_user**: The system user for Bitwarden service
  - Defaults to *bitwarden_user*
- **bitwarden_sh_url**: The URL that is the source of the Bitwarden shell file
  - Defaults to *https://raw.githubusercontent.com/bitwarden/server/master/scripts/bitwarden.sh*
- **external_domain**: The external domain that Bitwarden will be accessible by
  - Defaults to *bitwarden.example.com*
- **installation_id**: The installation ID given by Bitwarden. Must be changed for success
  - Defaults to *aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa*
- **installation_key**: The installation key given by Bitwarden. Must be changed for success
  - Defaults to *aaaaaaaaaaaaaaaaaaaa*
- **bitwarden_dir**: The directory to install Bitwarden in
  - Defaults to */opt/bitwarden*
- **smtp_host**: The host for SMTP for Bitwarden to send emails. Highly recommended
  - Defaults to *smtp.gmail.com*
- **smtp_port**: The port for SMTP for Bitwarden to send emails.
  - Defaults to *587*
- **smtp_ssl**: Whether SSL is in use for SMTP
  - Defaults to *true*
- **smtp_username**: The username for SMTP for Bitwarden to send emails. Highly recommended
  - Defaults to *my_user@gmail.com*
- **smtp_password**: The password for SMTP for Bitwarden to send emails. Highly recommended
  - Defaults to *my_password*
- **admin_user_email**: The user the email will appear to come from
  - Defaults to *bitwarden_admin@example.com*
- **cert_renewer_path**: The place to put the service that renews certificates
  - Defaults to */etc/systemd/system/cert-renewer@bitwarden.service.d*
- **environment_file**: The location of Bitwarden's environment file
  - Defaults to *{{ bitwarden_dir }}/bwdata/env/global.override.env*
- **reverse_proxy_servers**: The IP addresses for any Reverse Proxy Servers that will serve Bitwarden externally. Recommended to override.
  - Defaults to *[11.22.33.44, 55.66.77.88]*

Dependencies
------------

No role dependencies.

Example Playbooks
----------------

```yaml
# The bare minimum to deploy Bitwarden. The default SMTP uses Gmail
    - role: 'irontooch.homelab.cd_bitwarden'
      vars:
        external_domain: "bitwarden.mynewdomain.org"
        installation_id: "e840f3fb586d44689ca1f6e9cd7440d0e840"
        installation_key: "509ce20660e44d8980bc"
        smtp_username: "my_email_user@gmail.com"
        smtp_password: "my_email_password"
        reverse_proxy_servers:
          - 192.168.10.2
```

```yaml
# Use a seperate SMTP server other than Gmail with different SMTP settings and multiple reverse proxy servers
    - role: 'irontooch.homelab.cd_bitwarden'
      vars:
        external_domain: "bitwarden.mynewdomain.org"
        installation_id: "e840f3fb586d44689ca1f6e9cd7440d0e840"
        installation_key: "509ce20660e44d8980bc"
        smtp_username: "my_email_user@sendgrid.com"
        smtp_password: "my_email_password"
        smtp_host: "smtp.sendgrid.net"
        smtp_port: 25
        smtp_ssl: false
        reverse_proxy_servers:
          - 172.16.10.2
          - 172.16.20.2
```

License
-------

GPL v3.0

Author Information
------------------

Author is IronTooch
