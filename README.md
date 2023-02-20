**Gitlab in Docker Container**

If need to setup SMTP server settings, please append in GITLAB_OMNIBUS_CONFIG section
```
gitlab_rails['smtp_enable'] = true
gitlab_rails['smtp_address'] = "smtp.server"
gitlab_rails['smtp_port'] = 465
gitlab_rails['smtp_user_name'] = "smtp user"
gitlab_rails['smtp_password'] = "smtp password"
gitlab_rails['smtp_domain'] = "example.com"
gitlab_rails['smtp_authentication'] = "login"
gitlab_rails['smtp_enable_starttls_auto'] = true
gitlab_rails['smtp_openssl_verify_mode'] = 'peer'

# If your SMTP server does not like the default 'From: gitlab@localhost' you
# can change the 'From' with this setting.
gitlab_rails['gitlab_email_from'] = 'gitlab@example.com'
gitlab_rails['gitlab_email_reply_to'] = 'noreply@example.com'

# If your SMTP server is using a self signed certificate or a certificate which
# is signed by a CA which is not trusted by default, you can specify a custom ca file.
# Please note that the certificates from /etc/gitlab/trusted-certs/ are
# not used for the verification of the SMTP server certificate.
gitlab_rails['smtp_ca_file'] = '/path/to/your/cacert.pem'
```

You can enable SMTP connection pooling with the following setting:

```
gitlab_rails['smtp_pool'] = true
```
For furthur details, please refer to [Gitlab](https://docs.gitlab.com/omnibus/settings/smtp.html)