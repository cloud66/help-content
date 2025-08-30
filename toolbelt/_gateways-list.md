Lists all the gateway servers attached to a Cloud 66 account or organization.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx --org <organization_name> gateways list [--verbose]
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--org <organization_name> | no | — | The name of an organization in your Cloud 66 account |
| \--verbose | no | — | Display more detail about the gateways |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx --org my-compay gateways list --verbose
```

{% /tab %}
{% /tabs %}