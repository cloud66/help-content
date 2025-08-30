Remove a gateway from a Cloud 66 account.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx gateways remove --name <gateway name>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--name <gateway name> | yes | — | The name of the gateway |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx gateways remove --name aws_bastion
```

{% /tab %}
{% /tabs %}