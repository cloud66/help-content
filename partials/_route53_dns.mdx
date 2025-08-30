Amazon Route 53 requires an **API Access Key** and a **Secret Access Key** for an AWS account with (at least) the following permissions:

- `route53:ListHostedZones`
- `route53:GetChange`
- `route53:ChangeResourceRecordSets`

You can [assign permissions](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/r53-api-permissions-ref.html) to the account using an [IAM policy](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/access-control-overview.html) like the example below. You would need to replace the **Hosted Zone ID** for the example policy to work properly. 

```json
{
    "Version": "2012-10-17",
    "Id": "certbot-dns-route53 sample policy",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "route53:ListHostedZones",
                "route53:GetChange"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Effect" : "Allow",
            "Action" : [
                "route53:ChangeResourceRecordSets"
            ],
            "Resource" : [
                "arn:aws:route53:::hostedzone/YOURHOSTEDZONEID"
            ]
        }
    ]
}
```

To generate access keys for an account using your preferred method (web console or CLI)  by [following this guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html).

You can now add Route53 to your Cloud 66 account using these credentials ([see above](#set-up-a-dns-provider)).