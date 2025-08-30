You can use Cloud 66 to deploy your static site in any [DigitalOcean region](https://docs.digitalocean.com/products/platform/availability-matrix/).

Cloud 66 supports DigitalOcean API v2, which uses OAuth to authenticate requests. If you choose Digital Ocean as a deployment target you'll be redirected to the DigitalOcean Ocean site, where you need to authenticate and approve Cloud 66. Once confirmed you will be redirected back to Cloud 66, where you can deploy your application to your DigitalOcean account.

**DigitalOcean Spaces**

Static sites run on object storage. As such you will need to grant Cloud 66 access to Spaces Cloud Object Storage in your DigitalOcean account. To do this:

1. Log into your DigitalOcean account
2. Click on API in the left-hand navigation
3. Scroll down to Spaces Access Keys
4. Click Generate New Key
5. Give the key a name and click the tick button
6. Copy the Key ID and Key Secret and paste them somewhere secure
7. Add the Key ID and Key Secret during the next stage of set up (you also need to authenticate via OAuth as described below)



