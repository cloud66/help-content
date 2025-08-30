Add tags to a given entity.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx tags add --entity <entity type> --id <entity ID> --tags <tag>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--entity <entity type> | yes | — | The type of the entity |
| \--id <entity ID> | yes | — | The id of the entity |
| \--tags <tag> | yes | — | Tags to add to the given entity (can be multiple) |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx tags add --entity stack --id 12 --tags foo --tags bar
```

{% /tab %}
{% /tabs %}