---
title: Uninstalling MySQL
---

{% callout type="info" title="Need some help managing your MySQL Servers?" %}
[Try Cloud 66 Free](https://app.cloud66.com/users/sign_up?utm_source=-&utm_medium=-&utm_campaign=MySQL-top)

{% /callout %}

When using Cloud 66 to [deploy to your own servers](/docs/servers/registered-servers), you might experience trouble with an existing MySQL installation on your server.

Along with our general operating system requirements for the deployment to your server to work, we also recommend that you uninstall all MySQL related files from your server before deploying.

{% callout type="warning" title="Do not run on production servers" %}
 These commands are only intended to prepare fresh, standalone servers for initial provisioning. They should NOT be run on servers that are shared with your application or that are being used in production. 
{% /callout %}

Use apt to uninstall and remove all MySQL packages:
```shell
$ sudo apt-get remove --purge mysql-server mysql-client mysql-common -y
$ sudo apt-get autoremove -y
$ sudo apt-get autoclean
```

Remove the MySQL folder:

```shell
$ rm -rf /etc/mysql
```

Delete all MySQL files on your server:

```shell
$ sudo find / -iname 'mysql*' -exec rm -rf {} \;
```
Your system should no longer contain default MySQL related files.

{% callout type="info" title="Need some help managing your MySQL Servers?" %}
[Try Cloud 66 Free](https://app.cloud66.com/users/sign_up?utm_source=-&utm_medium=-&utm_campaign=MySQL-top)

{% /callout %}