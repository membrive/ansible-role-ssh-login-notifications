# Ansible Role: SSH Login Notifications

[![Build Status](https://travis-ci.org/membrive/ansible-role-ssh-login-notifications.svg?branch=master)](https://travis-ci.org/membrive/ansible-role-ssh-login-notifications)

Installs scripts to send a notification (by mail and/or Slack) when an user logs in using SSH.

The scripts use *pam_exec.so* in the PAM *open session* event to detect the login.

## Requirements

This role has been tested in Ubuntu 14.04 and Ubuntu 16.04 but it should be valid for any distribution that uses the PAM Linux system.

## Role Variables

The variables that can be passed to this role and a brief description about them are as follows.

```
# Notifications by email, set it to true to activate or false to deactivate
ssh_login_notifications_mail_enable: true

# Set the e-mail notification receiver
ssh_login_notifications_mail_receiver: "root"

# Notifications by Slack, set it to true to activate or false to deactivate
ssh_login_notifications_slack_enable: false

# Set the Slack custom integration webhook URL
ssh_login_notifications_slack_webhook: ""
```

Notifications previously activated with this role can be deactivated by setting the variable to *false*. 

## Dependencies

None

## Example Playbook

```
- hosts: server
  roles:
    - { role: membrive.ssh-login-notifications }
```

## License

MIT / BSD

## Author Information

This role was created in 2017 by [Fernando Membrive](https://membrive.net).
