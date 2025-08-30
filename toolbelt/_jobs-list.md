Lists all automated (scheduled) jobs on an application or a server.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx jobs list --stack <application name> --server <server name>|<server ip>|<server role> --service <service name>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--stack, -s <application name> | yes | — | Full or partial name of the application |
| \--server <server name>\|<server ip>\|<server role> | no | — | The name, IP address or role of the server. |
| \--service <service name> | no | — | The name of the service  |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx jobs list -s my-app
$ cx jobs list -s my-app --server orca
$ cx jobs list -s my-app --server 168.123.448.56 --service web
$ cx jobs list -s my-app --service web
```

{% /tab %}
{% /tabs %}