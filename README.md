# Ansible Playbooks #

Basic stuff for getting various personal servers running.

## mailserver ##

Fill in a mailserver using the example-com inventory as an example. Populate `files/mailserver.crt`
and `files/mailserver.key` with the server certificate and key.

To add a new user and password, update `/etc/dovecot/users`, which should be permissioned 640
dovecot:dovecot, with a username and password in the following format (ensuring that `user` matches
a unix user on the system):

`#user:password:uid:gid:(gecos):home:(shell):extra_fields`

Get the password by running `doveadm pw`, and fill in relevant information, e.g.:

`linda:{CRAM-MD5}63f73fd5c7d215dc84b3f55be69da501de920dd1a3db77968dd12e2880a037c3:500:500::/home/linda:`
