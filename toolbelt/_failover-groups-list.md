Lists the Failover Groups for a Cloud 66 account. Info includes the Failover Group ID, address, attached applications and current active application.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx failover-groups list [--output <view>]
```
{% /tab %}
    
{% tab label="arguments" %}
| Arguments | Required? | Default | Description |
| --- | --- | --- | --- |
| --output, -o \<view\> | no | standard | Tailor the output view (standard or wide) |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx failover-groups list -o wide
```

{% /tab %}
{% /tabs %}