Deletes an existing Failover Group from a Cloud 66 account.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx failover-groups delete --uid <failover UID>
```
{% /tab %}
    
{% tab label="arguments" %}
| Arguments | Required? | Default | Description |
| --- | --- | --- | --- |
| --uid \<failover UID\> | yes | — | The UID of the Failover Group to be deleted. |

{% /tab %}
{% tab label="examples" %}

```shell
$ cx failover-groups delete --uid "5999b763474b0eafa5fafb64bff0ba80"
```

{% /tab %}
{% /tabs %}