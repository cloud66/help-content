---
title:  "Using Passenger Enterprise"
---

Passenger is an open-source, popular multi-language (Ruby, Python, Node) web & app server which can integrate into Apache and Nginx. Cloud 66 offers enterprise customers the ability to deploy applications with Passenger Enterprise, which has several key benefits:

- Rolling restarts
- Concurrency and multi-threading
- Deployment error resistance
- Mass deployment
- Live IRB console
- Resource control and limiting
- Ruby debugger support

See the [Passenger Enterprise website](https://www.phusionpassenger.com/enterprise) for more information about benefits.

## Deploy with Passenger Enterprise
We require two simple steps to deploy with Passenger Enterprise:

1. Place your `passenger-enterprise-license` file into your .cloud66 folder, which in turn is located in the root of your repository.

2. Add a `PASSENGER_ENTERPRISE_DOWNLOAD_TOKEN` [environment variable](/docs/build-and-config/env-vars) which contains the value of your Passenger Enterprise download token.

If both these conditions are met, any Passenger-based server is deployed with the Enterprise edition installed. Ensure that Passenger Enterprise is displayed in the _About your app_ section of your analysis before deploying.

### Updating your license key

If you need to update or change your license key for any reason (e.g. to license a server that was deployed using the trial version of Passenger Enterprise), then you will need to:

1. Copy the new `passenger-enterprise-license` file into the .cloud66 folder (overwriting any existing file) 
2. Commit and push your code to your repository
3. In your app [Dashboard](https://app.cloud66.com/), click *Deploy* &rarr; *Deploy with Options* 
4. Check the *Apply Security Upgrades* box.
5. Click *Run Now* to deploy


{% callout type="info" title="Only install Enterprise on new servers"%}
We recommend that you choose Passenger Enterprise as your web server at the time of **initial build** of the application. If you already have an application, please [scale up](/docs/servers/scaling) to a new application server and scale down the old one to add Passenger Enterprise.
{% /callout %}