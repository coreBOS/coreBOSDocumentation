---
title: 'Confidential Information'
metadata:
    description: 'Extension to safely store sensitive information. Data will be encrypted and only accessible by users with the appropriate credentials. The goal of the module is to protect sensitive information both from unauthorized access from within the company and from anybody who could somehow get a hold of our full database, be them ill-intentioned or simply third parties that require access to support or solve problems.'
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
        - module
---
---
Extension to safely store sensitive information. Data will be encrypted and only accessible by users with the appropriate credentials. The goal of the module is to protect sensitive information both from unauthorized access from within the company and from anybody who could somehow get a hold of our full database, be them ill-intentioned or simply third parties that require access to support or solve problems.

===

### Fields

#### Confidential Information

<table class="table table-striped">
<thead>
<tr class="header">
<th>Field</th>
<th>Type</th>
<th>Values</th>
</tr>
</thead>
<tbody>
<tr>
<td>CI INFO No</td>
<td>autonumber</td>
<td><strong>Identifier</strong></td>
</tr>
<tr>
<td>CI Reference</td>
<td>string</td>
<td></td>
</tr>
<tr>
<td>CI Related to</td>
<td>relation</td>
<td>Accounts,Contacts</td>
</tr>
<tr>
<td>CI Category</td>
<td>picklist</td>
<td>— Please Select —,Access Information,Personal Information,Other Information</td>
</tr>
<tr>
<td>CI Asset</td>
<td>relation</td>
<td>Assets</td>
</tr>
<tr>
<td>Assigned To</td>
<td>assigned to</td>
<td></td>
</tr>
<tr>
<td>Created Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr>
<td>Modified Time</td>
<td>datetime</td>
<td></td>
</tr>
<tr>
<td>Description</td>
<td>text</td>
<td></td>
</tr>
</tbody>
</table>
<br>
#### Custom Information
<br>
#### Additional Information

### Confidential Information Module

This module is related to an account/contact and an asset. You will be able to see the list of associated confidential information records in the +info tab of the related entities.

A Confidential Info record will have two parts:

+ Header
 - CI Number (link field)
 - Account/Contact (mandatory)
 - Asset (optional)
 - Name, text field for reference
 - Category, picklist, exclusively for filtering purposes
 - Description
 - Created and Modified time
+ Rest of fields and blocks
 - All the rest of fields that are of text type will be encrypted, (even custom fields). Numbers, percent, currency, reference fields (uitype 10), checkbox, dates and time fields will NOT be encrypted as their values would be lost when saving to the database. If you need to encrypt numbers, create a text field and save the number there.

<div class="notices blue">
    <p>This module requires the use of the MySQLi php extension, it will NOT work correctly without it.</p>
</div>

It will not have comments support, nor import/export capabilities, among others.

<div class="notices blue">
    <p>Import could be easily activated but would only be useful in one situation, which is the initial import. If we import sensible information it will be imported in plain text. Once imported we could launch the initial encryption process and it would all be encrypted. After that, the import process would not work anymore as the information would (again) come in plain while the module expected it to be encrypted.</p>
</div>

It will have an automatic history log, similar to the existing functionality in tickets or potentials.

When trying to access detail or edit view, the user will automatically be prompted for a company-wide password. If it is given correctly, access will be granted and logged. If not, access will be denied and logged.

Once access has been granted, a time countdown will start. When the time has been consumed, the browser will be redirected to the Confidential Information list view, effectively hiding the information from sight. The length of this timer can be configured in Settings.

If a record is recovered from the **Recycle Bin** it should still be accessible even if the company password was changed in between deleting and recovering.

Internally all the information will be saved encrypted using PHP mcrypt library. The company password will be saved using sha1 hash and the necessary information vector will be changed each time the password is changed.

In module manager administration tools for the module, you will be able to change the company password. This is a global process that will decrypt ALL the information saved in the module and encrypt them again using the new password and information vector.

Since we are using standard encryption methods and following standards, if somebody does get a hold of your database, it should take them a VERY long time (years) to retrieve the company password necessary to decrypt the stored information, but, as usual with this type of requests and work, it is just as good as the passwords you use. If you decide to use your company name for the company-wide password, then it won't take anybody to long to get access to the information :-)

### How it works
To use this module, you install it using the module manager, then create the custom fields that you need to save the sets of confidential information you have.

This module **requires php_mcrypt** to be enabled in your PHP configuration as this extension is used to encrypt the information.

Next, you can access the **Change Password** section through module manager:

![Settings](cisettings.png?width=100%)

<br>
![Pass](cichgpass.png?width=100%)

Establish the company-wide password and you can start using the module as you would with any other module. The difference will be that you will be asked for the company password each time you try to access the detail or edit view. If you give it correctly you will be able to access the information, if not you will not be able to see the information.

### Recover Information on Lost Password

<div class="notices red">
    <p>If you lose the password you lose your information, there is nothing more to say.</p>
</div>
<div class="notices red">
    <p>Use this module at your own risk. We have not had any problems (yet), but we should not be held liable for any data loss or other events derived from the use of this module.</p>
</div>

### Libsodium Encryption
Alternatively to the mcrypt methods, we can also encrypt the information with the more secure libsodium library.

Here are some links on the benefits and how to install the library for it's use with PHP.

+ [Choosing the Right Cryptography Library for your PHP Project: A Guide](https://paragonie.com/blog/2015/11/choosing-right-cryptography-library-for-your-php-project-guide)
+ [Using Libsodium in PHP Projects](https://paragonie.com/book/pecl-libsodium/read/00-intro.md)
+ [Halite Project](https://github.com/paragonie/halite)
+ [Libsodium Project](https://github.com/jedisct1/libsodium-php)

### openSSL Encryption
Alternatively to the mcrypt methods, we can also encrypt the information with the more secure openSSL library.

Here are some links on the benefits and how to install the library for its use with PHP.

+ [Using openssl_en/decrypt() in PHP instead of Mcrypt](https://thefsb.tumblr.com/post/110749271235/using-opensslendecrypt-in-php-instead-of)
+ [How To Safely Generate A Random Number](https://sockpuppet.org/blog/2014/02/25/safely-generate-random-numbers/)

### PKI Encryption Methods
This method expects to find both the private and public key in some directory accessible from the coreBOS install. This means that the security of this method is inexistent. PKI security is based on how secure you can keep your private key. Since we have both public and private together, in the code, anyone who gets access to your code has direct access to the information.

So, why did we implement it? Because you can use the public key to encrypt the information and not save the private key in the system. If the private key does not exist, no information will be shown. If you need to access the information you must send it to some other system where the private key lives and decrypt it there.

### Other Encryption Methods
The module has a generalized layer for the encryption and decryption actions making it fairly easy to implement other ways of protecting your information.

If you are interested, you can contact us for help or have a look at this article that explains how that can be done. **here is a link**

### Confidential Information as an Encryption/Decryption Engine
As with most of the development we create, we try to create infrastructure, things you can use in your own developments, not just functionality. Once an encryptionmethod is configured, you can use this module to encrypt and decrypt any information anywhere in the application. For example, in after_save event or in some hook,…

This is what a small script to encrypt a couple of values looks like:

```php
include 'vtlib/Vtiger/Module.php';
include_once 'modules/ConfidentialInfo/ConfidentialInfo.php';
 
$info = array('text'=>'text example','num'=>'123.456');
$encrypted = ConfidentialInfo::encryptFields_pki($info, 'file://public.key');
 
var_dump($encrypted);
 
$decrypted = ConfidentialInfo::decryptFields_pki($encrypted, 'file://private.key');
 
var_dump($decrypted);
```
### Future Enhancements
Future options to consider in design (not in scope yet)

<div class="notices red">
<p>IMPORTANT
resume password change. If the password change is interrupted information will be lost, this must be fixed. The solution is to save the previous decrypt information until the whole process is done and mark each record as processed as they are changed. This way we can continue on non-processed records if something goes wrong without losing information.
IMPORTANT
If anybody wants to sponsor this contact me</p></div>

+ Dual password login (like using SMS as second password)
+ Access per category/user (so some users only can access category 1 other category 2)
+ Option to force admin renew password after n-days.

!! With the help and support of [Object Solutions](https://www.specpage.com/), Thanks!!




