First you need to configure your AWS account to allow Cloud 66 to access it:

1. Log into the web interface for your AWS account
2. Click on the name of your account in the top right corner of your AWS account, and select *My Security Credentials*.

On the next screen, some users will be asked to choose between *Security Credentials* and *IAM users*. We support both methods but we recommend that experienced users select IAM (*Identity and Access Management*) for better security because allows you to set permissions for specific users. Click on your chosen option below for more instructions.

{% collapsible title="Option A: Using root credentials" %}

After selecting the **Security Credentials** option: 

1. Select the *Access Keys* option from the menu. 
2. Click *Create new access key*
3. Either download the key file or click *Show access key* and take note of your access key ID and secret access key. These are the credentials needed for Cloud 66 to access your account.

{% /collapsible %}

{% collapsible title="Option B: Identity Access Management (IAM)" %}

*Step 1: Create a user*

After selecting the **IAM option** follow [this guide in AWS docs](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html) to set up a new IAM user for Cloud 66. We recommend naming the user `cloud66` for clarity.

Be sure to copy or save the **Access Key ID** and **Secret Access Key** for this user - you will need these credentials to connect your Cloud 66 account.

*Step 2: Set up access policies*

You'll need to assign access policies for the `cloud66` user so that it will have the access it requires to provision and manage your sites. 

You can see them here: [recommended minimum policies](https://help.cloud66.com/c66_prepress_aws_iam_policy.json).

There are two method for assigning policies: using the AWS CLI or the web console:

{% collapsible title="AWS CLI" %}

If you have the AWS CLI tool installed, you can set up your access policies by running this command:

```shell
curl https://help.cloud66.com/c66_prepress_aws_iam_policy.json > c66_prepress_aws_iam_policy.json && aws iam put-user-policy --user-name cloud66 --policy-name ExamplePolicy --policy-document file://c66_prepress_aws_iam_policy.json
```

This downloads our JSON template to your machine and then submits it via the CLI. Note that this assumes you have named your user `cloud66` as recommended. You can find more info in the [AWS docs](https://docs.aws.amazon.com/cli/latest/reference/iam/put-user-policy.html) if you need it.

{% /collapsible %}

{% collapsible title="Web console" %}

You can add policies via the IAM management console.

1. Click on Access management → Users
2. Click on your `cloud66` user
3. Click the *Add inline policy* button
4. In another browser tab Open our [JSON template](https://help.cloud66.com/c66_prepress_aws_iam_policy.json) and copy the whole page to your clipboard
5. Back in the IAM console, click the JSON tab and paste in the template you just copied
6. Click *Review Policy*
7. Give your policy a name
8. Click *Create Policy*

If you need more detail please read the [AWS docs](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html#add-policies-console) on this subject.

{% /collapsible %}

{% /collapsible %}


