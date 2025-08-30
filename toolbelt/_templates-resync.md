Pulls the latest code from the stencil template repository for a specific template.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx templates resync --template <template UID>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--template <template UID>  | yes | — | The UID of the template that will be refreshed |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx templates resync --template 'bt-2e0810a17c33ab35d7970ff330b1f916'
```

{% /tab %}
{% /tabs %}