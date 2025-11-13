# gitlab

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/gitlab)
[![General Workflow](https://github.com/rolehippie/gitlab/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/gitlab/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/gitlab/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/gitlab/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/gitlab/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/gitlab/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/gitlab)](https://github.com/rolehippie/gitlab/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.gitlab-blue)](https://galaxy.ansible.com/rolehippie/gitlab)

Ansible role to install and configure Gitlab.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [gitlab_backup_keep_time](#gitlab_backup_keep_time)
  - [gitlab_backup_path](#gitlab_backup_path)
  - [gitlab_backup_upload_location](#gitlab_backup_upload_location)
  - [gitlab_backup_upload_remote_directory](#gitlab_backup_upload_remote_directory)
  - [gitlab_block_auto_created_users](#gitlab_block_auto_created_users)
  - [gitlab_config_backup_day](#gitlab_config_backup_day)
  - [gitlab_config_backup_enabled](#gitlab_config_backup_enabled)
  - [gitlab_config_backup_hour](#gitlab_config_backup_hour)
  - [gitlab_config_backup_job](#gitlab_config_backup_job)
  - [gitlab_config_backup_minute](#gitlab_config_backup_minute)
  - [gitlab_config_backup_month](#gitlab_config_backup_month)
  - [gitlab_config_backup_path](#gitlab_config_backup_path)
  - [gitlab_config_backup_post](#gitlab_config_backup_post)
  - [gitlab_config_backup_pre](#gitlab_config_backup_pre)
  - [gitlab_config_backup_script](#gitlab_config_backup_script)
  - [gitlab_config_backup_weekday](#gitlab_config_backup_weekday)
  - [gitlab_content_backup_day](#gitlab_content_backup_day)
  - [gitlab_content_backup_enabled](#gitlab_content_backup_enabled)
  - [gitlab_content_backup_hour](#gitlab_content_backup_hour)
  - [gitlab_content_backup_job](#gitlab_content_backup_job)
  - [gitlab_content_backup_minute](#gitlab_content_backup_minute)
  - [gitlab_content_backup_month](#gitlab_content_backup_month)
  - [gitlab_content_backup_path](#gitlab_content_backup_path)
  - [gitlab_content_backup_post](#gitlab_content_backup_post)
  - [gitlab_content_backup_pre](#gitlab_content_backup_pre)
  - [gitlab_content_backup_script](#gitlab_content_backup_script)
  - [gitlab_content_backup_weekday](#gitlab_content_backup_weekday)
  - [gitlab_default_theme](#gitlab_default_theme)
  - [gitlab_domain](#gitlab_domain)
  - [gitlab_download_validate_certs](#gitlab_download_validate_certs)
  - [gitlab_email_display_name](#gitlab_email_display_name)
  - [gitlab_email_enabled](#gitlab_email_enabled)
  - [gitlab_email_from](#gitlab_email_from)
  - [gitlab_email_reply_to](#gitlab_email_reply_to)
  - [gitlab_external_url](#gitlab_external_url)
  - [gitlab_extra_config](#gitlab_extra_config)
  - [gitlab_git_data_dir](#gitlab_git_data_dir)
  - [gitlab_keyring](#gitlab_keyring)
  - [gitlab_letsencrypt_auto_renew](#gitlab_letsencrypt_auto_renew)
  - [gitlab_letsencrypt_auto_renew_day_of_month](#gitlab_letsencrypt_auto_renew_day_of_month)
  - [gitlab_letsencrypt_auto_renew_hour](#gitlab_letsencrypt_auto_renew_hour)
  - [gitlab_letsencrypt_auto_renew_minute](#gitlab_letsencrypt_auto_renew_minute)
  - [gitlab_letsencrypt_contact_emails](#gitlab_letsencrypt_contact_emails)
  - [gitlab_letsencrypt_enable](#gitlab_letsencrypt_enable)
  - [gitlab_omniauth_allow_bypass_two_factor](#gitlab_omniauth_allow_bypass_two_factor)
  - [gitlab_omniauth_allow_single_sign_on](#gitlab_omniauth_allow_single_sign_on)
  - [gitlab_omniauth_auto_link_user](#gitlab_omniauth_auto_link_user)
  - [gitlab_omniauth_providers](#gitlab_omniauth_providers)
  - [gitlab_prune_daily_day](#gitlab_prune_daily_day)
  - [gitlab_prune_daily_enabled](#gitlab_prune_daily_enabled)
  - [gitlab_prune_daily_hour](#gitlab_prune_daily_hour)
  - [gitlab_prune_daily_job](#gitlab_prune_daily_job)
  - [gitlab_prune_daily_minute](#gitlab_prune_daily_minute)
  - [gitlab_prune_daily_month](#gitlab_prune_daily_month)
  - [gitlab_prune_daily_path](#gitlab_prune_daily_path)
  - [gitlab_prune_daily_post](#gitlab_prune_daily_post)
  - [gitlab_prune_daily_pre](#gitlab_prune_daily_pre)
  - [gitlab_prune_daily_script](#gitlab_prune_daily_script)
  - [gitlab_prune_daily_weekday](#gitlab_prune_daily_weekday)
  - [gitlab_prune_weekly_day](#gitlab_prune_weekly_day)
  - [gitlab_prune_weekly_enabled](#gitlab_prune_weekly_enabled)
  - [gitlab_prune_weekly_hour](#gitlab_prune_weekly_hour)
  - [gitlab_prune_weekly_job](#gitlab_prune_weekly_job)
  - [gitlab_prune_weekly_minute](#gitlab_prune_weekly_minute)
  - [gitlab_prune_weekly_month](#gitlab_prune_weekly_month)
  - [gitlab_prune_weekly_path](#gitlab_prune_weekly_path)
  - [gitlab_prune_weekly_post](#gitlab_prune_weekly_post)
  - [gitlab_prune_weekly_pre](#gitlab_prune_weekly_pre)
  - [gitlab_prune_weekly_script](#gitlab_prune_weekly_script)
  - [gitlab_prune_weekly_weekday](#gitlab_prune_weekly_weekday)
  - [gitlab_redirect_http_to_https](#gitlab_redirect_http_to_https)
  - [gitlab_registry_domain](#gitlab_registry_domain)
  - [gitlab_registry_enable](#gitlab_registry_enable)
  - [gitlab_registry_external_url](#gitlab_registry_external_url)
  - [gitlab_registry_nginx_ssl_certificate](#gitlab_registry_nginx_ssl_certificate)
  - [gitlab_registry_nginx_ssl_certificate_key](#gitlab_registry_nginx_ssl_certificate_key)
  - [gitlab_smtp_address](#gitlab_smtp_address)
  - [gitlab_smtp_authentication](#gitlab_smtp_authentication)
  - [gitlab_smtp_ca_file](#gitlab_smtp_ca_file)
  - [gitlab_smtp_ca_path](#gitlab_smtp_ca_path)
  - [gitlab_smtp_domain](#gitlab_smtp_domain)
  - [gitlab_smtp_enable](#gitlab_smtp_enable)
  - [gitlab_smtp_enable_starttls_auto](#gitlab_smtp_enable_starttls_auto)
  - [gitlab_smtp_openssl_verify_mode](#gitlab_smtp_openssl_verify_mode)
  - [gitlab_smtp_password](#gitlab_smtp_password)
  - [gitlab_smtp_port](#gitlab_smtp_port)
  - [gitlab_smtp_tls](#gitlab_smtp_tls)
  - [gitlab_smtp_user_name](#gitlab_smtp_user_name)
  - [gitlab_ssl_certificate](#gitlab_ssl_certificate)
  - [gitlab_ssl_certificate_key](#gitlab_ssl_certificate_key)
  - [gitlab_time_zone](#gitlab_time_zone)
  - [gitlab_version](#gitlab_version)
  - [gitlan_external_url](#gitlan_external_url)
  - [gitlan_registry_path](#gitlan_registry_path)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### gitlab_backup_keep_time

Time to keep backups for

#### Default value

```YAML
gitlab_backup_keep_time: 604800
```

### gitlab_backup_path

Path to store the backups

#### Default value

```YAML
gitlab_backup_path: /var/opt/gitlab/backups
```

### gitlab_backup_upload_location

Upload location for backups

#### Default value

```YAML
gitlab_backup_upload_location:
```

### gitlab_backup_upload_remote_directory

Remote upload directory

#### Default value

```YAML
gitlab_backup_upload_remote_directory:
```

### gitlab_block_auto_created_users

Block autocreated users

#### Default value

```YAML
gitlab_block_auto_created_users: false
```

### gitlab_config_backup_day



#### Default value

```YAML
gitlab_config_backup_day: '*'
```

### gitlab_config_backup_enabled



#### Default value

```YAML
gitlab_config_backup_enabled: false
```

### gitlab_config_backup_hour



#### Default value

```YAML
gitlab_config_backup_hour: '03'
```

### gitlab_config_backup_job



#### Default value

```YAML
gitlab_config_backup_job: /usr/bin/cronic {{ gitlab_config_backup_path }}
```

### gitlab_config_backup_minute



#### Default value

```YAML
gitlab_config_backup_minute: '00'
```

### gitlab_config_backup_month



#### Default value

```YAML
gitlab_config_backup_month: '*'
```

### gitlab_config_backup_path



#### Default value

```YAML
gitlab_config_backup_path: /usr/local/bin/gitlab-backup-config
```

### gitlab_config_backup_post



#### Default value

```YAML
gitlab_config_backup_post:
```

### gitlab_config_backup_pre



#### Default value

```YAML
gitlab_config_backup_pre:
```

### gitlab_config_backup_script



#### Default value

```YAML
gitlab_config_backup_script: gitlab-ctl backup-etc --delete-old-backups
```

### gitlab_config_backup_weekday



#### Default value

```YAML
gitlab_config_backup_weekday: '*'
```

### gitlab_content_backup_day



#### Default value

```YAML
gitlab_content_backup_day: '*'
```

### gitlab_content_backup_enabled



#### Default value

```YAML
gitlab_content_backup_enabled: false
```

### gitlab_content_backup_hour



#### Default value

```YAML
gitlab_content_backup_hour: '03'
```

### gitlab_content_backup_job



#### Default value

```YAML
gitlab_content_backup_job: /usr/bin/cronic {{ gitlab_content_backup_path }}
```

### gitlab_content_backup_minute



#### Default value

```YAML
gitlab_content_backup_minute: '00'
```

### gitlab_content_backup_month



#### Default value

```YAML
gitlab_content_backup_month: '*'
```

### gitlab_content_backup_path



#### Default value

```YAML
gitlab_content_backup_path: /usr/local/bin/gitlab-backup-content
```

### gitlab_content_backup_post



#### Default value

```YAML
gitlab_content_backup_post:
```

### gitlab_content_backup_pre



#### Default value

```YAML
gitlab_content_backup_pre:
```

### gitlab_content_backup_script



#### Default value

```YAML
gitlab_content_backup_script: gitlab-backup create
```

### gitlab_content_backup_weekday



#### Default value

```YAML
gitlab_content_backup_weekday: '*'
```

### gitlab_default_theme

Default theme for Gitlab

#### Default value

```YAML
gitlab_default_theme: 2
```

### gitlab_domain

Domain to access Gitlab

#### Default value

```YAML
gitlab_domain: git.example.com
```

### gitlab_download_validate_certs

Validate download certificates

#### Default value

```YAML
gitlab_download_validate_certs: true
```

### gitlab_email_display_name

Name used for email configuration

#### Default value

```YAML
gitlab_email_display_name: Gitlab
```

### gitlab_email_enabled

Enable email configuration

#### Default value

```YAML
gitlab_email_enabled: false
```

### gitlab_email_from

From used for email configuration

#### Default value

```YAML
gitlab_email_from: gitlab@example.com
```

### gitlab_email_reply_to

Reply used for email configuration

#### Default value

```YAML
gitlab_email_reply_to: gitlab@example.com
```

### gitlab_external_url

#### Default value

```YAML
gitlab_external_url: https://{{ gitlab_domain }}/
```

### gitlab_extra_config

Optional additional configuration for gitlab.rb config file

#### Default value

```YAML
gitlab_extra_config:
```

### gitlab_git_data_dir

Data directory for repositories

#### Default value

```YAML
gitlab_git_data_dir: /var/opt/gitlab/git-data
```

### gitlab_keyring

Path for the repository keyring

#### Default value

```YAML
gitlab_keyring: /usr/share/keyrings/gitlab-archive-keyring.gpg
```

### gitlab_letsencrypt_auto_renew

Enable autorenew for LEts Encrypt

#### Default value

```YAML
gitlab_letsencrypt_auto_renew: true
```

### gitlab_letsencrypt_auto_renew_day_of_month

Daf of month to renew Lets Encrypt certificates

#### Default value

```YAML
gitlab_letsencrypt_auto_renew_day_of_month: '*/7'
```

### gitlab_letsencrypt_auto_renew_hour

Hour to renew Lets Encrypt certificates

#### Default value

```YAML
gitlab_letsencrypt_auto_renew_hour: 1
```

### gitlab_letsencrypt_auto_renew_minute

Minute to renew Lets Encrypt certificates

#### Default value

```YAML
gitlab_letsencrypt_auto_renew_minute: 30
```

### gitlab_letsencrypt_contact_emails

List of contact mail adresses for Lets Encrypt

#### Default value

```YAML
gitlab_letsencrypt_contact_emails:
  - gitlab@example.com
```

### gitlab_letsencrypt_enable

Enabled Lets Encrypt configuration

#### Default value

```YAML
gitlab_letsencrypt_enable: false
```

### gitlab_omniauth_allow_bypass_two_factor

#### Default value

```YAML
gitlab_omniauth_allow_bypass_two_factor: []
```

### gitlab_omniauth_allow_single_sign_on

List of Omniauth methods to allow single signon

#### Default value

```YAML
gitlab_omniauth_allow_single_sign_on: []
```

### gitlab_omniauth_auto_link_user

List of Omniauth methods to bypass 2FA.

#### Default value

```YAML
gitlab_omniauth_auto_link_user: []
```

### gitlab_omniauth_providers

List of Omniauth providers

#### Default value

```YAML
gitlab_omniauth_providers: []
```

### gitlab_prune_daily_day



#### Default value

```YAML
gitlab_prune_daily_day: '*'
```

### gitlab_prune_daily_enabled



#### Default value

```YAML
gitlab_prune_daily_enabled: false
```

### gitlab_prune_daily_hour



#### Default value

```YAML
gitlab_prune_daily_hour: '02'
```

### gitlab_prune_daily_job



#### Default value

```YAML
gitlab_prune_daily_job: /usr/bin/cronic {{ gitlab_prune_daily_path }}
```

### gitlab_prune_daily_minute



#### Default value

```YAML
gitlab_prune_daily_minute: '00'
```

### gitlab_prune_daily_month



#### Default value

```YAML
gitlab_prune_daily_month: '*'
```

### gitlab_prune_daily_path



#### Default value

```YAML
gitlab_prune_daily_path: /usr/local/bin/gitlab-prune-daily
```

### gitlab_prune_daily_post



#### Default value

```YAML
gitlab_prune_daily_post:
```

### gitlab_prune_daily_pre



#### Default value

```YAML
gitlab_prune_daily_pre:
```

### gitlab_prune_daily_script



#### Default value

```YAML
gitlab_prune_daily_script: gitlab-ctl registry-garbage-collect
```

### gitlab_prune_daily_weekday



#### Default value

```YAML
gitlab_prune_daily_weekday: 1-6
```

### gitlab_prune_weekly_day



#### Default value

```YAML
gitlab_prune_weekly_day: '*'
```

### gitlab_prune_weekly_enabled



#### Default value

```YAML
gitlab_prune_weekly_enabled: false
```

### gitlab_prune_weekly_hour



#### Default value

```YAML
gitlab_prune_weekly_hour: '02'
```

### gitlab_prune_weekly_job



#### Default value

```YAML
gitlab_prune_weekly_job: /usr/bin/cronic {{ gitlab_prune_weekly_path }}
```

### gitlab_prune_weekly_minute



#### Default value

```YAML
gitlab_prune_weekly_minute: '00'
```

### gitlab_prune_weekly_month



#### Default value

```YAML
gitlab_prune_weekly_month: '*'
```

### gitlab_prune_weekly_path



#### Default value

```YAML
gitlab_prune_weekly_path: /usr/local/bin/gitlab-prune-weekly
```

### gitlab_prune_weekly_post



#### Default value

```YAML
gitlab_prune_weekly_post:
```

### gitlab_prune_weekly_pre



#### Default value

```YAML
gitlab_prune_weekly_pre:
```

### gitlab_prune_weekly_script



#### Default value

```YAML
gitlab_prune_weekly_script: gitlab-ctl registry-garbage-collect -m
```

### gitlab_prune_weekly_weekday



#### Default value

```YAML
gitlab_prune_weekly_weekday: '0'
```

### gitlab_redirect_http_to_https

Always redirect HTTP to HTTPS

#### Default value

```YAML
gitlab_redirect_http_to_https: true
```

### gitlab_registry_domain

Domain to access registry

#### Default value

```YAML
gitlab_registry_domain: registry.example.com
```

### gitlab_registry_enable

Enable registry configuration

#### Default value

```YAML
gitlab_registry_enable: false
```

### gitlab_registry_external_url

Full external URL to access registry

#### Default value

```YAML
gitlab_registry_external_url: https://{{ gitlab_registry_domain }}
```

### gitlab_registry_nginx_ssl_certificate

Path to registry SSL certificate

#### Default value

```YAML
gitlab_registry_nginx_ssl_certificate: /etc/gitlab/ssl/gitlab.crt
```

### gitlab_registry_nginx_ssl_certificate_key

Path to registry SSL certificate key

#### Default value

```YAML
gitlab_registry_nginx_ssl_certificate_key: /etc/gitlab/ssl/gitlab.key
```

### gitlab_smtp_address

Address for SMTP connection

#### Default value

```YAML
gitlab_smtp_address:
```

### gitlab_smtp_authentication

Authentication for SMTP connection

#### Default value

```YAML
gitlab_smtp_authentication: login
```

### gitlab_smtp_ca_file

Path to CA certificate file for SMTP connections

#### Default value

```YAML
gitlab_smtp_ca_file: /etc/ssl/certs/ca-certificates.crt
```

### gitlab_smtp_ca_path

Path to CA certificates for SMTP connection

#### Default value

```YAML
gitlab_smtp_ca_path: /etc/ssl/certs
```

### gitlab_smtp_domain

Domain for SMTP connection

#### Default value

```YAML
gitlab_smtp_domain:
```

### gitlab_smtp_enable

Enable SMTP configuration

#### Default value

```YAML
gitlab_smtp_enable: false
```

### gitlab_smtp_enable_starttls_auto

Enable STARTTLS for SMTP connection

#### Default value

```YAML
gitlab_smtp_enable_starttls_auto: true
```

### gitlab_smtp_openssl_verify_mode

Verify SSL for SMTP connection

#### Default value

```YAML
gitlab_smtp_openssl_verify_mode: none
```

### gitlab_smtp_password

Password for SMTP connection

#### Default value

```YAML
gitlab_smtp_password:
```

### gitlab_smtp_port

Port for SMTP connection

#### Default value

```YAML
gitlab_smtp_port: 465
```

### gitlab_smtp_tls

Enable TLS for SMTP connection

#### Default value

```YAML
gitlab_smtp_tls: false
```

### gitlab_smtp_user_name

Username for SMTP connection

#### Default value

```YAML
gitlab_smtp_user_name:
```

### gitlab_ssl_certificate

Path for SSL certificate

#### Default value

```YAML
gitlab_ssl_certificate: /etc/gitlab/ssl/{{ gitlab_domain }}.crt
```

### gitlab_ssl_certificate_key

Path for SSL certificate key

#### Default value

```YAML
gitlab_ssl_certificate_key: /etc/gitlab/ssl/{{ gitlab_domain }}.key
```

### gitlab_time_zone

Timezone used for Gitlab

#### Default value

```YAML
gitlab_time_zone: UTC
```

### gitlab_version

Version of Gitlab that gets installed

#### Default value

```YAML
gitlab_version: 18.1.1
```

### gitlan_external_url

Full external URL to access Gitlab

### gitlan_registry_path

Path to store registry data

#### Default value

```YAML
gitlan_registry_path:
```

## Discovered Tags

**_gitlab_**

## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
