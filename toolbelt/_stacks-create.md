Creates a new Cloud 66 application based on a service definition (`service.yml`) and an optional application Manifest (`manifest.yml`).

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx stacks create --name <new application name> --service_yaml <service definition>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--name, -n <new application name> | yes | — | Name for the new application |
| \--service_yaml <service definition> | yes | — | The YAML formatted service definition file  |
| \--manifest_yaml, -m | no | — | Manifest definition for the new application (YAML formatted file) |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx stacks create --name my_cloud66_app --service_yaml service.yml --manifest_yaml manifest.yml
```

{% /tab %}
{% /tabs %}