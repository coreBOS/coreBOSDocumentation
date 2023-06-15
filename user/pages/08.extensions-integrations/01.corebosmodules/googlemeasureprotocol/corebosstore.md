---
title: 'Google Measurement Protocol Extension'
metadata:
    description: 'integrate Google Measurement Protocol with coreBOS using workflows'
    author: 'Joe Bordes'
content:
    items:
        - '@self.children'
    limit: 5
    order:
        by: date
        dir: desc
    pagination: true
    url_taxonomy_filters: true
taxonomy:
    category:
        - extension
    tag:
        - google
        - gmp
---

This extension permits you to send data to Google Analytics based on ClientID on Account via WorkfFlow. With this easy setup you can fully track the ROI of your google investments and do all sorts of analysis and statistics on your clients using Google Analytics platform.

===

## Setup

To setup the integration you must execute three actions.

### Access to Google Account

Go to Settings &gt; Module manager &gt; Custom modules and click on the settings/hammer on the *Google Measurement Protocol* line to access the configuration screen where you will put the necessary information to access google analytics. These are your website google analytics ID and the version of the GMP that you are using.

![](googlemeasurementprotocol01.png?width=100%)

### Mark your Accounts, Contacts and/or Leads

As your users navigate through your website, Google assigns them a unique identifier. They call it *Google Analytics ClientID*. We need to attach to each account or contact created in the CRM this identifier. You can get this ID using javascript after loading the Google Analytics code. Once you have this number you must send it to the CRM. The normal process will be something like this:

Your user reaches your website, Google adds his identifier to your statistics. When the user decides to contact you he fills in the webform, when you send the information from the form you also send the Google Identifier and save it on a custom field in the CRM.

<div class="notices blue"> If you are creating Accounts, the "Google Analytics ClientID" field already exists. </div>

<div class="notices red">If you add a "Google Analytics ClientID" field to Leads, remember to add the mapping of that value into Accounts or Contacts.</div>

### Send your closing information

Once the prospect is inside the CRM you can follow your normal opportunity management process, until you reach the "Closed Lost" or "Closed Won" status. At this point you will create a workflow to send the relevant information that you want to register in Google Analytics.

For example, you can simply send the information of the status of the opportunity, or, if the client actually buys the service you can detect the creation of a sales order or invoice and send that fact, with the amounts to Google Analytics. Since we will be sending also the Google Identifier you will be able to track the sales and return on investment easily.

To send the information you create a workflow and construct the URL to send to Google using meta-variables from the record being saved.

In the examples below we send sales order totals to Analytics.

![](googlemeasurementprotocol02.png?width=100%)

![](googlemeasurementprotocol03.png?width=100%)

