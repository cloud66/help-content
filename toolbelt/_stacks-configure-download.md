Download configuration files such as a *service.yml* or *manifest.yml*. (containerized apps only)

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx stacks configure download --file <filename> --stack <application name> --output <output path>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--stack, -s <application name> | yes | — | Name of the application |
| \--file, -f <filename> | yes | — | Name of the config file. Accepted values: `service.yml`,`manifest.yml` |
| \--output, -o <output path> | no | — | Full path of the output file. |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx stacks configure download -f service.yml -s myapp -o /c66/config-files/service.yml
```

{% /tab %}
{% /tabs %}