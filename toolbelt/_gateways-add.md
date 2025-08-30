Add a gateway server to a Cloud 66 account.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx gateways add --name <gateway name> --address <gateway address> --username <gateway username> --private-ip <private ip of gateway>
```
{% /tab %}
    
{% tab label="arguments" %}
| Argument | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--name <gateway name> | yes | — | The name of the gateway |
| \--address <gateway address> | yes | — | The IP address of the gateway |
| \--username <gateway username> | yes | — | The username for accessing the gateway |
| \--private-ip <private ip of gateway> | yes | — | The private IP address to use to access the network behind the gateway |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx gateways add --name aws_bastion --address 192.168.100.100  --username ec2-user  --private-ip 192.168.1.1
$ cx --org My_Awesome_org gateways add --name aws_bastion --address 1.1.1.1  --username ec2-user  --private-ip 192.168.2.2
```

{% /tab %}
{% /tabs %}