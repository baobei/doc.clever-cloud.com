---
title: FAQ
position: 3
---

## Clever Cloud FAQs

### What is a Scaler?

A <dfn id="def-scaler">scaler</dfn> is a individual container hosting your app. You can attribute one or more Scalers to your apps. Scalers comes in many sizes based on each language requirement from XS to XXXL.

Each [scaler](#def-scaler) is given a fixed set of resources, depending on the chosen language. A Java [scaler](#def-scaler) will have more RAM than a PHP [scaler](#def-scaler).
The way you scale an application is by assigning it new [scalers](#def-scaler).
When enabling auto-scalability, you have to set a minimum and a maximum of active [scalers](#def-scaler) in your apps settings. This way you can prcisely control your monthly fee.

### What languages and frameworks are supported by Clever Cloud?

Currently Clever Cloud supports:

* Java (Play Framework 1 & 2, Maven, War files… )
* Node.js
* PHP ([see frameworks and CMS](/php/php-apps/#frameworks-and-cms))
* Python (Django)
* Ruby
* Go

### How many applications can I create with Clever Cloud?

As much as you want. We've not set a limited number of apps by developer.

### How can I disable one of my existing applications?

Log in with your account to [console.clever-cloud.com](https://console.clever-cloud.com), and select the appropriate organisation and app in the head-bar. Then click on **Configuration** in the left pane to stop your app. It will be un-deployed, and ready for a new start without pushing your app via Git or FTP again.

### What type of content is allowed on Clever Cloud?

Please refer to our Terms and Conditions, article 6, *Obligations and responsibilities of the client*.

### How is the current load report in my application's admin console generated?

We use custom probes to monitor :

* hardware's components usage
* databases read / write / update operations

### How do I authenticate members of my organisation?

Log in with your account to [console.clever-cloud.com](https://console.clever-cloud.com), and select the appropriate organisation in the head-bar. Then click on **Configuration** in the left pane and select **Members**. You'll see a list of the organisation's members. If your are an admin, you can revoke or grant apps permissions.

### How do I report an application that is in violation of your Terms and Conditions?

To report an application that is in violation of the Clever Cloud's Terms and Condition, please contact us at <abuse@clever-cloud.com>.

We will investigate and contact the application's owner over the violation if needed.

### Does Clever Cloud support SSL (HTTPS)?

Absolutely! For now, it's not automatic. Contact us at <support@clever-cloud.com>, we will enable it for you. Custom SSL certificates will be available directly in Clever Cloud very soon.

### I'd like to map my app to http://mydomain.com.

See [Custom Domain Names](/admin-console/apps-management/#custom-domain-names) section of Apps Management.

### How do I define cron jobs for my application?

This feature is currently only available for PHP, Python and Ruby applications. See [Cron Configuration File](/php/php-apps/#cron-configuration-file) for more information.

### How many active requests can my app serve at one time?

There are two possibilities, according to the scalability settings you've opted for.

1. You have set a single [scaler](#def-scaler) : the maximum active requests depends on your [scaler's](#def-scaler) computing limits.
2. You have set auto-scalability, new [scalers](#def-scaler) will be started as long as your app need more resources (until it reaches the maximum number of [scalers](#def-scaler) you have defined).

### How to know if a user comes from a secure connection?

All connections are handled by load-balancers ahead of your applications and forwarded in plain http, you cannot rely on the server port to know the scheme used by the user.

Instead of it you can use the `X-Forwarded-Proto` HTTP header to get the information, it is set to '*http*' or '*https*'.

<div class="alert alert-hot-problems">
   <h4>Note for Play Framework! 1.2.x users</h4>
   <p>In order to use `request.secure` instead of accessing the header, you must add `XForwardedSupport=all` in your *application.conf*.</p>
</div>
