---
title: 'Google Contacts Synchronization'
metadata:
    description: 'Google Contacts Synchronization'
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
        - google
        - integration
    tag:
        - contacts
---

### Google Contacts Synchronization

- You must have the Google OAuth project configured with Google Contacts API enabled.
- Go to the Contacts list view
- Click on the "Google Contacts" button
- If this is the first time you access click on the "Sign in with Google" button and authorize access to your contacts information on Google
- Click on the button again and select the "Sync Settings" button
- Select a group to sync with, the fields and the direction of the synchronization
- It is interesting to sync a group instead of all your contacts in order to keep things organized
- From this point forward any changes that you make in either of the applications will get synchronized when you click on the "Sync Now" button

### Configure Google OAuth Access

In order to enable the Google Contacts synchronization, it is necessary to create a project in the Google developer's console. If you already have one created for the [Google Calendar integration](../../../08.extensions-integrations/03.calendar-google/01.calendar_google_integration) you can use this same one by simply enabling the Google Contacts API.

Let's suppose that you do not have a project already and we need to create a new one.

- Go to the Google Developers Console by accessing [this link](https://console.developers.google.com/project).
- Select a project, or create a new one by clicking Create Project.
- In the Project name field, type in a name for your project.
- In the Project ID field, optionally type in a project ID for your project or use the one that the console has created for you. This ID must be unique worldwide.
- Click the Create button and wait for the project to be created.
- Click on the new project name in the list to start editing the project.
- In the sidebar under "APIs & auth", select Consent screen.
- Choose an Email Address and specify a Product Name.
- If you can fill in the Logo, privacy and terms URLs, better.
- Note that it is VERY important to fill in the Consent screen [**BEFORE** proceeding to create the credentials](http://stackoverflow.com/questions/23775972/error-invalid-client-with-google-apps-api-oauth2#answer-27707551)
- In the sidebar under "APIs & auth", select Credentials.
- Click Create a new Client ID — a dialog box appears.
- Register the origins from which your app is allowed to access the Google APIs, as follows. An origin is a unique combination of protocol, hostname.
- In the Application type section of the dialog, select Web application.
- In the Authorized JavaScript origins field, enter the origin for your app. You can enter multiple origins to allow for your app to run on different protocols, domains, or subdomains.
  - Wildcards are not allowed. In the example below, the second URL could be a production URL.
    - <http://localhost:8080>
    - <https://myproductionurl.example.com>
- In the "Authorized redirect URIs" put this URL:
```
http://your_host/your_coreBOS/index.php?module=Contacts&action=ContactsAjax&file=List&operation=sync&sourcemodule=Contacts&service=GoogleContacts
```
- Click the Create Client ID button.
- In the resulting Client ID for web application section, copy the Client ID that your app will need to use to access the APIs.
- After completion, you will get a client id and client secret id.
- After this you will need to [add the email to this group](https://groups.google.com/forum/#!forum/risky-access-by-unreviewed-apps) according to new Google rules to protect user’s data
- Under **"Google Apps API"** click "Contacts API" link
- Click the ENABLE button
- Now we have to activate the integration and set the project values in coreBOS
- Go to this URL in your coreBOS install:
```
http://your_host/your_coreBOS/index.php?module=Utilities&action=integration&_op=getconfiggcontact
```
- Introduce the API key and OAuth credentials.
- Activate the integration and save the settings

### Batch Synchronizations

The contacts information is sent to Google in batches of 200 records. This can be changed using the **GContacts\_Max\_Results** global variable
