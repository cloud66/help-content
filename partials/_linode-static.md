You can use Cloud 66 to deploy your static site in any [Linode region](https://developers.cloud66.com/#linode-2).

You need to generate a personal access token for your Linode account to grant Cloud 66 access. To do this:

1. Log into [Linode Cloud Manager](https://cloud.linode.com/)
2. Click on your username at the top of the screen and select *My Profile*.
3. Click *API Tokens* and then *Add a Personal Access Token*
4. Give the token a label and set its expiry to `Never`
5. Set the access rights for the token to a minimum of:`Account: Read-onlyDomains: Read/WriteKubernetes: Read/WriteLinodes: Read/WriteNodeBalancers: Read/WriteVolumes: Read/Write`
6. Click *Create Token* and then copy the personal access token.

You will use this token to add Linode as a Deployment Target (see below).