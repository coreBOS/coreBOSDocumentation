---
title: 'Google Measurement Protocol Extension'
---

Google Measurement Protocol Extension
=====================================

This extension permits you to send data to Google Analytics based on
ClientID on Account via WorkfFlow. With this easy setup you can fully
track the ROI of your google investments and do all sorts of analysis
and statistics on your clients using Google Analytics platform.  
---- dataentry ---- name : tsolucio/cbGMP type : corebos-extension
description\_wiki: This extension permits you to send data to Google
Analytics based on ClientID on Account via WorkfFlow. With this easy
setup you can fully track the ROI of your google investments and do all
sorts of analysis and statistics on your clients using Google Analytics
platform. keywords\_tags :
Google,Measurement,ROI,payment,click,advertising,adwords,adclicks,Analytics,analysis,statistics
version : 1.0 homepage\_url :
<http://corebos.org/documentation/doku.php?id=en:extensions:extensions:googlemeasurementprotocol>
release\_dt : 2015-07-02 licenses : Vizsage price : 310eur
buyemail\_mail : paypal(at)tsolucio(dot)com distribution : Sale
authorname : JPL TSolucio, S.L. authoremail\_mail :
info(at)tsolucio(dot)com supportemail\_mail : info(at)tsolucio(dot)com

------------------------------------------------------------------------

  

Setup
=====

To setup the integration you must execute three actions.

Access to Google Account
------------------------

Go to Settings &gt; Module manager &gt; Custom modules and click on the
settings/hammer on the *Google Measurement Protocol* line to access the
configuration screen where you will put the necessary information to
access google analytics. These are your website google analytics ID and
the version of the GMP that you are using.

<img src="/en/extensions/extensions/gmp/googlemeasurementprotocol01.png" class="align-center" width="800" />

Mark your Accounts, Contacts and/or Leads
-----------------------------------------

As your users navigate through your website, Google assigns them a
unique identifier. They call it *Google Analytics ClientID*. We need to
attach to each account or contact created in the CRM this identifier.
You can get this ID using javascript after loading the Google Analytics
code. Once you have this number you must send it to the CRM. The normal
process will be something like this:

Your user reaches your website, Google adds his identifier to your
statistics. When the user decides to contact you he fills in the
webform, when you send the information from the form you also send the
Google Identifier and save it on a custom field in the CRM.

&lt;WRAP center round info 80%&gt; If you are creating Accounts, the
"Google Analytics ClientID" field already exists. &lt;/WRAP&gt;

&lt;WRAP center round important 80%&gt; If you add a "Google Analytics
ClientID" field to Leads, remember to add the mapping of that value into
Accounts or Contacts. &lt;/WRAP&gt;

Send your closing information
-----------------------------

Once the prospect is inside the CRM you can follow your normal
opportunity management process, until you reach the "Closed Lost" or
"Closed Won" status. At this point you will create a workflow to send
the relevant information that you want to register in Google Analytics.

For example, you can simply send the information of the status of the
opportunity, or, if the client actually buys the service you can detect
the creation of a sales order or invoice and send that fact, with the
amounts to Google Analytics. Since we will be sending also the Google
Identifier you will be able to track the sales and return on investment
easily.

To send the information you create a workflow and construct the URL to
send to Google using meta-variables from the record being saved.

In the examples below we send sales order totals to Analytics.

<img src="/en/extensions/extensions/gmp/googlemeasurementprotocol02.png" class="align-center" width="800" />

<img src="/en/extensions/extensions/gmp/googlemeasurementprotocol03.png" class="align-center" width="800" />
