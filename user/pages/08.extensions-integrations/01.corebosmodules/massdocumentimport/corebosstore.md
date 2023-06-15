---
title: 'Mass Document Import'
metadata:
    description: 'coreBOS extension that permits mass import of documents'
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

coreBOS extension that permits mass import of documents

===

### How it works

This works like this:

- It is a vtlib compatible extension, so it is installed via the **module manager** interface.
- Once installed you must edit the `filelocation.php` configuration file to change the import directory variable `$filedirectory`. This directory is where the documents must be copied and from where the extension will read them and import them. Alternatively, you can add the global variable `MDI_File_Import_Directory` and set it to the path of the directory where the files to import are.
- When you access the extension you are greeted with an edit document screen that asks for a reference, user, folder and description. When Save is clicked the import process will read documents in from the established folder on the harddisk. Each document will have the format: **id_filename.ext** We will search for **id** as **contact ID number**, if not found, we search for it as **account ID number**. We will insert a new document in the system assigned to the selected user, in the chosen folder, with the given title and description, associated to the contact/account if found and with the name `filename.ext`
- If no account/contact is found the document is not imported
- If document is imported, it is eliminated from the directory
- there is a special value for the title name: `__FILENAME__`, this special value will create the records setting the document record title to the name of the file
- there are two business map fields that can hold a coreBOS Rule and modify the way the import works
  - `bmfoldername` returns a document folder ID or name to relate with the imported document. The rule gets the context variable `filename`
  - `bmrelation` returns a CRMID of a record to relate with the imported document. The rule gets the context variable `filename`

We can change the logic to associate to any other entity or by any other field.

### Q & A

**Should I manually change the file name of the documents to import?**
<hr>
Yes, you will have to change their names to adapt to the format expected by the plugin. It currently expects to find the Contact or Account ID number but we can adapt that if you already have your files in some other format. For example, for a client here in Spain, where each citizen has a unique ID card number we have a version that looks for this number in a custom field of the contacts.
<br>

**Do you think I can import 3000 documents in one upload?**
<hr>
You should be able to import 3000 in one shot with no problem, but it will all depend on the capacity and configuration of your server, that is why the extension eliminates the files once imported. Thanks to that feature, if it stops for any reason you just launch it again and it will continue.
<br>

**Example If i have a document called 12345.pdf and contact name Adam Smith, what will be the file name of the document?**
<hr>
Supposing that the contact Adam Smith has a Contact ID of: CON987, then the file must be renamed to: CON987_12345.pdf to be imported.
<br>

**If I import all those files, can I still add more file to each contact?**
<hr>
Yes, of course, the imported documents are simply normal coreBOS documents that will live along side all the others you may upload in other ways before or after.

