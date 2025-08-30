Upload configuration files such as a *service.yml* or *manifest.yml*. (containerized apps only)

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx stacks configure upload --file <filename> --stack <application name> --comments <comment>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--stack, -s <application name> | yes | — | Name of the application |
| \--file, -f <filename> | yes | — | Name of the config file. Accepted values: `service.yml`,`manifest.yml` |
| \--comments, -c <comment> | yes | — | A brief description of your changes |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx stacks configure upload -f service.yml -s myapp -c "updates to ports"
```

{% /tab %}
{% /tabs %}