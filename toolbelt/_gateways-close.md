Close a gateway (prevents traffic flowing via the gateway).

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx gateways close --name <gateway name>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--name <gateway name> | yes | — | The name of the gateway |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx gateways close --name aws_bastion
```

{% /tab %}
{% /tabs %}