---
title: 'Generic Javascript API Access to backend: Execute Function'
---

Generic Javascript API Access to backend: Execute Function
==========================================================

&lt;WRAP center round box 60%&gt; **Execute Function**: How to call the
application backend from javascript &lt;/WRAP&gt;

During front-end development, we normally run into situations where we
need information from the backend or we need some functionality that is
already implemented there with all the necessary logic.

Obviously, this where javascript AJAX comes into play and we launch a
call to the backend to retrieve the information or operations that we
need.

There are mostly three ways to do this:

-   AJAX File: you add a file in some module's directory and call it
    with a specific URL. See below how we call ExecuteFunctions which is
    the exact same case
-   Webservices: you extend the users session and can use all the
    webservice API power
-   ExecuteFunctions: is a generic API to access certain functionality
    in the application

We can call the ExecuteFunctions API through the Utilities module, like
this:

    var url = "module=Utilities&action=UtilitiesAjax&file=ExecuteFunctions";
    var url = url + "&functiontocall=getModuleWebseriviceID&wsmodule=Accounts";
    fetch('index.php?'+ url, {
        credentials: 'same-origin'
    }).then(function(response) {
        return response.text();
    }).then(function(data) {
        console.log('Accounts webservice ID is: ' + data);
    });

Which in my chrome developer console, sending the request to the
coreBOSTest database, looks like this:

<img src="/en/devel/execfunx01.png" class="align-center" />

We also have a generic javascript funtions which avoids from having to
type the whole AJAX call. Using this function the above example would
be:

    ExecuteFunctions('getModuleWebseriviceID','wsmodule=Accounts').then(function(data) {
        console.log('Accounts webservice ID is: ' + data);
    });

**Which is MUCH NICER!**

In the chrome developer console this looks like this:

<img src="/en/devel/execfunc02.png" class="align-center" />

&lt;WRAP center round info 90%&gt; We enhance the list of supported
actions in ExecuteFunctions regularly so [have a look at the latest
copy](https://github.com/tsolucio/corebos/blob/master/modules/Vtiger/ExecuteFunctions.php)
to see all the things that can be done and don't hesitate to ask if you
find something missing that you think should be there. &lt;/WRAP&gt;

This is the list of actions that can be found:

-   **getFieldAutocomplete**: search for records in some modules
    -   @param searchinmodule: comma separated list of modules to search
        in
    -   @param term: string to search for
    -   @param fields: fields to look for the term in
    -   @param returnfields: fields to return of the records found
    -   @param limit: maximum number of records that will be returned
    -   @return set of records that have the term in the indicated
        fields
-   **getReferenceAutocomplete**: same as **getFieldAutocomplete** but
    searches only in the reference field of the defined modules and
    returns only those fields
-   **getFieldValuesFromRecord**: very useful function that permits
    getting information from QueryGenerator. You can find [an example in
    the Assets
    module](https://github.com/tsolucio/corebos/blob/master/modules/Assets/Assets.js#L57)
    which fills in the Account when an Invoice is selected
-   **getEmailTemplateDetails**: function to load a merged email
    template
-   **ValidationExists**: returns yes/no if a module has a custom
    validation script
-   **ValidationLoad**: execute the custom validations of a module
-   **getModuleWebseriviceID**: a quick way to get webservice module ID,
    faster than ListTypes and parsing the output.
-   **getEmailTemplateVariables**: get a list of template variables
-   **saveAttachment**: upload an image or file to the application
-   **getNumberDisplayValue**: format the given values in the currency
    of the user
-   **ismoduleactive** returns boolean indicating if the given module is
    active or not in the installation
