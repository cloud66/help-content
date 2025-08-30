List all the stencils in a formation.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx formations stencils list --formation <formation name> --output <view>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--stack, -s <application name> | yes | — | Full or partial name of the application |
| \--formation <formation name> | yes | — | The name of the Formation to which the Stencils belong. |
| \--output <view> | no | standard | Tailor the output view (standard or wide) |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx formations stencils list --formation foo 
$ cx formations stencils list --formation bar --output wide
```

{% /tab %}
{% /tabs %}