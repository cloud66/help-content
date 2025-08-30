Shows information about your account, toolbelt and the specified stack or the current directory.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx info --stack <application name --unmanaged
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--stack, -s <application name> | no | — | Full or partial name of the application |
| \--unmanaged | no | — | Lists the servers under your cloud account that are NOT in any of your applications. |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx info -s my-application --unmanaged
```

{% /tab %}
{% /tabs %}