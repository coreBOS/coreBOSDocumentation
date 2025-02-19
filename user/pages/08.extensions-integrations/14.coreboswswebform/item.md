---
title: 'coreBOS Webservice Webform'
metadata:
    description: 'coreBOS advanced webform creation and validation'
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
        - development
        - webservice
    tag:
        - webform
---

<a href="https://github.com/tsolucio/coreBOSwsWebform">Get the code on GitHub</a>

## coreBOS advanced webform creation and validation 
<div class="notices blue">
This project takes webforms to the next level. </div>

![](coreboswswebform.png?width=100%)

<img src="coreboswswebform.png" alt="">


coreBOS has a native webform creation and implementation feature that permits us to create a webform for a given module (accounts, contacts, leads, potentials, helpdesk,…) but in many cases, somebody filling in information on our website isn't just one entity in coreBOS. For example, somebody filling in a contact form may already be interested in some product and should be converted into a Contact **AND** an Opportunity, or when filling in a support form we should get a Contact **AND** a HelpDesk. That is what this project does, it is an easy way to convert fields captured from our webform into different entities in coreBOS.

While we were at it we added the **typical validation of fields**, so you can make sure a given field is not repeated or already exists before sending the information in to the application.

## Configuration and Usage

The general idea is to set up your web form with whatever tool best fits your website software and have the form data sent to a script that will set the configuration options and call the coreBOS Webservice Webform code. This script will validate the information, connect to the defined coreBOS system and create the configured entities.

You have to copy the coreBOS Webservice Webform code to some server you have access to. The *WsWebform.php* script must be accessible from your webform as when your user clicks on the send button the whole form must be redirected to this script.

In the same place you have copied the *WsWebform.php* script you must also create a directory *cbwsclib* and copy inside the <a href="https://github.com/tsolucio/coreBOSwsLibrary/tree/master/php">PHP coreBOS Webservice Library</a>
. This library adds the functionality yo connect to your coreBOS to do the validations and inserts.

All the configuration options are contained in an array at the beginning of your script:

```php
* $config = array(
      // Connection parameters
      'url' => 'http://localhost/corebos/',  // your coreBOS system URL
      'user' => 'admin',  // user that will be connecting via REST to create the entities and validate fields
      'password' => '',  // user's access key
      // Entity mapping to process form fields
      'map' => array(
          // WebServices module name
          'Contacts' => array(
              // Field mapping
             'fields' => array(
                  // [Entity field name] => [form field name]
                  'firstname' => 'firstname',
                  // Use just the field name if both are the same
                  'lastname',
                  'email',
              ),
              // Fields that should match to find a duplicate
              'matching' => array(
                  // we can specify an 'and' or 'or' key to group fields inside parenthesis with the given operator, nesting is possible
                  'or' => array(
                      'and' => array(
                          // [field name in the dabase] => [field name in the new entity]
                          'firstname' => 'firstname',
                          // When both are the same we can write just one
                          'lastname',
                      ),
                      'email',
                  ),
                  // The resulting condition is ( ( firstname=e.firstname and lastname=e.lastname ) or email=e.email )
              ),
              // Optionally, an entity can include other related entities
              'has' => array(
                  // We repeat here the structure for an Entity mapping
                  'Potentials' => array(
                      'fields' => array(
                          'related_to' => '[Contacts]',
                          'potentialname' => 'potential_name',
                          'closingdate' => 'potential_closingdate',
                          'sales_stage' => 'potential_sales_stage',
                      ),
                      'matching' => array(
                          // When no operator is specified, 'and' is used, so here all fields should match
                          'related_to',
                          'potentialname',
                      ),
                  ),
              ),
          ),
          // We could go on with other entity mappings
      ),
  );
```

The abstract idea is that you define two things:

-   access information to your coreBOS
-   list of modules to create in the coreBOS system


For each module you want to create you can define:

-   **'fields':** list of fields in the coreBOS system that you want to save and which fields on the form are capturing that information
-   **'matching':** a set of validation steps you want to verify against the coreBOS system, basically avoid duplicate records based on some fields
-   **'has':** a list of modules, for each one we will create a new record related to the main module of this configuration option. The definition of each module has the exact same structure and functionality as the main module of this setting.

The <a href="https://github.com/tsolucio/coreBOSwsWebform">GitHub repository</a> has a <a href="https://github.com/tsolucio/coreBOSwsWebform/blob/master/test.php">test</a> file which you can use as a starting point for your project.

[plugin:youtube](https://www.youtube.com/watch?v=gv0NV95iOPo)
<br>
<br>
## Questions and Answers

<div class="notices blue">
<strong>I am using Gravity Forms hook, and it sends the field value not the full form data. So when your script parses it doesn't accept the value because its trying to find something else. 
</strong> <br>
<a href="https://www.gravityhelp.com/documentation/article/gform_after_submission/#2-send-entry-data-to-third-party">https://www.gravityhelp.com/documentation/article/gform_after_submission/#2-send-entry-data-to-third-party</a> 
</div>

Do this:
```php
add_action( 'gform_after_submission', 'post_to_third_party', 10, 2 );
function post_to_third_party( $entry, $form ) {
    require_once('WsWebform.php');
    $config = array(...);  // define your config array here to connect
    $webform = new WsWebform($config);    
    $body = array(
        'first_name' => rgar( $entry, '1.3' ), 
        'last_name' => rgar( $entry, '1.6' ), 
        'message' => rgar( $entry, '3' ),
    );
    $webform->send($body);
// check for errors
}
```

*Relaying a Webform* |[Read more](./webforms)

<br>
------------------------------------------------------------------------

[Next](../11.skipconvertfields)| Chapter 17: Skip convert fields.


------------------------------------------------------------------------