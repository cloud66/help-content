Reboot a specific server.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx servers reboot --stack <application name> --server <server name>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--stack, -s <application name> | yes | — | Name of the application |
| \--server <server name> | yes | — | The name of the server to reboot |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx server reboot --stack my-app --server lion
```

{% /tab %}
{% /tabs %}