Download a managed database backup via the command line. If the backup spans multiple files, the command will automatically concatenate them into a single file.

{% tabs %}
{% tab label="Usage" %}

```shell
$ cx backups download --stack <application name> [--download <download directory>] <backup id>
```
{% /tab %}
    
{% tab label="arguments" %}
| Arguments | Required? | Default | Description |
|  ---  |  ---  |  ---  |  ---  |
| \--stack, -s <application name> | yes | — | The name of the application |
| \--directory, -d <download directory> | no | — | The local directory in which to save the downloaded file |
| <backup ID> | yes | — | The backup ID (you can get this using the backup list command) |
{% /tab %}
{% tab label="examples" %}

```shell
$ cx backups download -s mystack -d /tmp/backups 23212
```
{% /tab %}
{% /tabs %}


{% callout type="info" title="Managed backups only" %}
This command only applies to managed backups and not the unmanaged ones.
{% /callout %}
