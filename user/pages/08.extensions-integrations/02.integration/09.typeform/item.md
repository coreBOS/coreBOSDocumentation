---
title: 'Typeform Configuration'
metadata:
    description: 'It is a web based platform you can use to create anything from surveys to apps, without needing to write a single line of code.'
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
        - integration
    tag:
        - typeform 
---
---
### Typeform Configuration

Configuring the application to read Typeform surveys consists of various
steps detailed next:

-   Create the survey in Typeform
-   Create a notification by email for the survey. The email must have
    this subject:
    ```php
    Typeform::<surveyid>::<surveyurl>`
    ```
    -   *surveyid* is the internal identifier assigned by Typeform
    -   *surveyurl* is the url of the survey

![](cbcrm_survey_typeform_config.png?width=100%)



-   Configure Email Converter in the application so it can read the
    Typeform notifications

![](cbcrm_typeform_scanner_config.png?width=100%)

-   Configure the Typeform API access key in **Settings &gt;
    Configuration Editor**
-   That's it, with those two changes, coreBOSCRM will receive an email
    each time a survey is completed and it will be registered in the
    application.
-   Now you can create workflows associated to the creation event of the
    different records to have the system act upon them.

### Typeform Implementation

-   Read surveyid from mail subject
-   Read typeform json
-   If survey doesn't exist &gt; create it with stats and info
-   If it exists &gt; update stats
-   Foreach questions &gt; upsert
-   Foreach responses
    -   Get ACL and email
    -   Attach email to ACL
    -   Check if done
    -   If exists &gt; ignore
    -   If not &gt; create with meta data
    -   Foreach answer &gt; create answer
    -   Update lastsync datetime

**TBD FIXME:** Check all this, document it!

-   Limitation. Only works with existing ACL. **??? Really, no anonymous
    surveys ??? \#\#\#\#\#\#**

------------------------------------------------------------------------

[Next](../10.webdav) | Chapter 10: Integration with Sabre/DAV WebDAV

------------------------------------------------------------------------