---
title: Setting and managing environment variables
---

## Overview 

One of the benefits of using Formations and Stencils is that you can define environment variables centrally and then pull them into different configuration files as you need them, using the powerful [Stencil Placeholder syntax](/docs/skycap/stencil-placeholders).

You can create, edit and manage environment variables for each of your applications via your Cloud 66 dashboard.

## What you’ll need

Before you start, please check you have the following:

* **A Cloud 66 Account** &mdash; If you don't already have one [sign up for a Cloud 66 account](https://app.cloud66.com/users/sign_up). Your first server is free, no credit card required.

* **An existing application set up in Skycap** &mdash; You can learn how to do that with our [Getting started with Skycap](/docs/skycap/getting-started) guide.

* **An existing Formation defined in Skycap** &mdash; You can learn how to do that with our [Getting started with Skycap Formations](/docs/skycap/using-formations) guide.

{% callout type="info" title="Sample project" %}
 In this example we’re using the same [simple "hello world" project](https://github.com/cloud66-samples/helloworld.git) that we used in our Getting Started guides and our other tutorials. 
{% /callout %}

## Setting environment variables for an application

Let’s imagine you’ve decided to set the ports for your Hello World service via an environment variable rather than directly in your stencils.

To achieve this, we need to four things:

1. Add an environment variable to the application via the Cloud 66 dashboard
2. Take a new Snapshot of the application (to enable the new variable to be called)
3. Edit the Stencil for the service in question (in our case `helloworld_service.yml`)
4. Render the Formation to see that the variable is being pulled through correctly

### Adding a custom variable

To add our variable, we:

1. Open your [Cloud 66 dashboard](https://app.cloud66.com/dashboard) and click on the *Hello World* application
2. Click on ⚙️ *Settings* in the left-hand nav
3. Click on *Environment Variables* in the sub-nav that opens
4. Add the key name `DEV_PORT` and the value `80`
5. Click *Save Changes*

This will add our custom variable to the application as a whole, but it won’t be available to use in our Stencils until we take a new Snapshot

### Ingesting new variables via a Snapshot

Before a newly added custom environment variable can be used in your Stencils (or elsewhere in your application), you need to take a fresh Snapshot of your application. This is because Snapshots encapsulate environment variables at a specific point in time (which enables rollbacks and other useful features).

To take a Snapshot, click the green *Snapshot* button at the top right of the screen and select *Snapshot all*. Once the build process is complete, we can begin using our new variable in our Stencils.

### Calling variables in Stencils

Now we need to pull our new `DEV_PORT` variable into our `helloworld_service.yml` Stencil. We do this using a snippet of [Stencil Placeholder](/docs/skycap/stencil-placeholders) syntax:

1. Click on *Formations* in the left-hand nav
Click on the edit icon next to the “Hello World” service Stencil
2. Find the `port` and replace the hardcoded value (“8080”) with `${env("DEV_PORT")}`
3. Add a commit message and click *Save Changes*

### Rendering variables 

To see whether our new variable is working correctly, we need to render our Formation and then check the contents of the Stencil we just edited. To do this:

1. Ensure you’re on the Formation page for your Hello World application
2. Click on the *Render Formation* button below the Stencil list. This will render out all your stencils
3. Scroll down to your `helloworld_service.yml` and click the *show all* link
4. Check that the value for *port* matches our variable (i.e. `80`)

## Importing multiple variables

It's possible to import multiple environment variables into a Stencil at once, as well as filter which variables are imported, using the `envlist` Stencil placeholder.

If you'd like to learn how to do this, follow our [dedicated envlist guide](/docs/skycap/reusing-common-environment-variables).

## Uploading and downloading variable files

You can manage your environment variables in bulk by uploading them in a `.txt` file with each variable declared on a separate line, and key value pairs separated by `=` signs. The Key should always be in uppercase.

For example:
```shell
DEV_PORT=80
LIVE_PORT=8080
FOO=Bar
YES=Green
``` 

To upload a file:

1. Navigate to the *Environment variables* page for the application in question (as above)
2. At the top of the panel, click the *Choose file* button and select the file
3. Your list of variables will immediately update to reflect the new variables (or changes to existing variables.
4. Click *Save changes* to save them into your application (changes will be discarded unless you do this)

{% callout type="info" title="Uploading variables" %}
 Uploading variable files is *additive* not subtractive. It will add new variables to your existing list, but will not remove any existing variables. It will, however, update any existing variables if you have changed the value of any of the keys. 
{% /callout %}

### Downloading variables as a file

You can also download your existing variables in the same format by clicking the *Download file* on the same page (below the left-hand nav). This will produce a `.txt` file in the same format described above.

{% callout type="warning" title="Be careful" %}
 You can use this feature to quickly update large numbers of variables, but be wary of accidentally updating any values while doing so. 
{% /callout %}

## What’s next?

* How to [import entire sets](/docs/skycap/reusing-common-environment-variables) of common variables into Stencils
* Learn how to [update an existing service](/docs/skycap/updating-an-existing-service) in Skycap.
* Learn how to [add new services or components](/docs/skycap/adding-a-new-service) to a service.
* Learn how to [roll back to an older version of your application](/docs/skycap/rolling-back-using-snapshots) using Snapshots.
* Learn how to set up [access control and permissions](/docs/skycap/setting-up-access-control) on your Formations and Stencils
* Learn how to use your [Habitus build flow](/docs/skycap/using-habitus-with-skycap) within Skycap.
* Learn how to use [validation policies](/docs/skycap/using-validation-policies) to ensure your Stencils adhere to your standards and conventions. 

