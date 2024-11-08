---
title: 'Importing Data::Basic functionality'
metadata:
    description: 'The import feature enables users to import data or records from various sources into coreBOS.'
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
        - importing
    tag:
        - data
        - import
---

The import feature enables users to import data or records from various sources into coreBOS. Currently, CSV, JSON and VCF (Vcard) format are allowed to import. (Exceptionally iCal import is supported for Calendar module).

===

Export/Import feature is enabled on almost all modules. There are a few that are still not supported like price books or FAQ and Documents whose import process is more complex and is supported by an external tool which is not free (ask us if you need it).

Steps to Import
---------------

### Step 1: Select File

After clicking on Import icon, the first step is to select the file. Click on the Browse button to select a file from your local system and upload it to the server for Import. Currently, csv and vcf formats are accepted.

![](importcontacts.png?width=100%)

### Step 2: Specify Format

![](specifyformat.png?width=100%)


#### File Type

- csv and vcf (vcard) are the 2 file types, currently supported.
- Character Encoding: Make sure you select the right character set in which your import file has been encoded. Just because file has UTF-8 characters in it, do not expect the tool to import the UTF-8 characters in right format, by selecting UTF-8 encoding. You need to ensure you select the right encoding of the file irrespective of the file contents.

Following 2 sections, apply only for csv file import:

#### Delimiter

Currently comma(,) and semi-colon(;) are supported as field delimiters. This delimiter indicates the character separator used to separate field values from each other within a row. In the case that you need to use the same character in your data and do not want the tool to read it as delimiter, enclose the string in double quotes ("). Then, only delimiter characters, outside the double quotes, will be treated as actual delimiter.

#### Has Header

The 'Has Header' property is to indicate whether the csv file has a header row or not. If you indicate that the csv file has a header, then the first row from the csv file is treated to be header and skipped from importing into the csv file. Having a header in the csv file, makes it easier for the user to map the csv columns to right CRM fields.

### Step 3: Duplicate Record Handling

This is an optional step, which allows you to configure duplicate record handling during Import. You can configure the criteria, for duplicate records look up and can also configure the action to be taken when duplicate records are found.

![](handleduplicates.png?width=100%)


- Select the action to be taken on duplicate records. Actions allowed are:
  - Skip: When a record from the import file is a duplicate of an already existing record in the CRM, then that record is skipped from importing into the system.
- Overwrite: When a record from the import file, has duplicate records in the CRM, all the existing duplicate records in the CRM are deleted except for the last one. The last duplicate record is overwritten by the newly imported record from the file.
- Merge: When a record from the import file, has duplicate records in the CRM, all the existing duplicate records in the CRM are deleted except for the last one. Only the non-empty values from the newly imported record from the file, are overwritten on the last duplicate record of the system.
- Skip record creation (only update): By default, if the record we are trying to import isn't a duplicate of an already existing record in the CRM, a new record with be created. If this button is on, instead of creating the new record, it will skip it.
- Select a rule to decide if the record is duplicate or not: If you select a Business Map here the Matching Fields will be ignored. The map can be a Condition Query or Condition Expression business map, that MUST return an array of duplicate IDS or a comma-separated list of duplicated IDs.

We have implemented a new workflow expression:

```
executeSQL(query, parameters...)
```

that can be used inside a condition expression map as the following example:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<map>
  <expression>executeSQL('SELECT accountid FROM vtiger_account INNER JOIN vtiger_crmentity ON vtiger_crmentity.crmid=vtiger_account.accountid WHERE vtiger_crmentity.deleted=0 AND vtiger_account.accountname=?',substring(accountname,0,10))</expression>
</map>
```
This map will return the ids of the non deleted account records, whose account name matches with the 10 first characters of the column mapped with accountname in the file. Based on the Duplicates Handle Method chosen the records with the ids returned might be skipped/overwritten/merged.

- Select the fields for duplicate records lookup: Configure the combination of fields, based on which the duplicate records need to be searched for. All the records which have the same values for the combination of the selected fields will be considered as duplicate records.

### Step 4: Map Columns to Module Fields

The last step is to configure the mapping between the import file columns/headers to the Module fields.

![](mapcolumns.png?width=100%)

- When importing CSV file, if the csv file has header, and the header name matches with the Field label, then those columns are automatically mapped.
- Default values can be provided for the mapped fields, which will be picked up, in case the value for the field in the file is empty.
- Mandatory fields need to be compulsorily mapped.
- If value of the mandatory fields is empty, they will be set to the string '????'.
- A particular field cannot be mapped more than once.

#### Saved Maps

- Commonly used mapping can be saved and re-used.
- Saved maps are accessible across all users.
- When a particular map is picked up from the selected list, the save mapping information reflects by mapping the fields configured for the map.
- Saved maps can also be deleted.

![](contacts.png?width=100%)

Import Process
--------------

### Terminology

- **Immediate Import Threshold** – Record count configured for immediate import. Value is configured through modules/Import/config.inc and the default value is set to 1000.
- **Batch Import Threshold** – Record count configured for batch import. Value is configured through modules/Imoprt/config.inc and the default value is set to 250.
- **Scheduled Import** - Import which is carried out through cron job which is generally configured to be run for every 15 minutes.

### Process

Clicking on Import button in Step 4, triggers Import.

- If number of records in file is less than 'Immediate Import Threshold', then import starts immediately. Otherwise, Import is scheduled and is triggered when the cron job runs (generally configured to run for every 15 minutes).
- When immediate import is triggered, 'Batch Import Threshold' decides the number of records to be imported as a batch and the status is available to the user on the screen.

<div class="notices blue">
<strong>1.</strong> When a user triggers import in one particular module, the user cannot start another import in the same or any other modules of the CRM.
</strong>2.</strong> When user X triggers import on a particular module, no other users can trigger import on the same module, whereas they can trigger import on other modules of the CRM.</div>

### Intermediate status update

![](importrunning.png?width=100%)

### Final Result of the Import

![](importfinalresult.png?width=100%)

- **Cancel Import** - Stops import abruptly leaving behind, partially imported records.
- **Import More** – Lets to start another import
- **Last Imported Records** – Allows you to view the records imported during the last/current import in a popup window with paging support.

![](lastimportedrecords.png?width=100%)

- **Undo Last Import** – Deletes all the records created during the last/current import.
- Undo Last Import option is available only during Import which do not involve duplicate record handling.
- Undo Last Import only deletes the records of the current module where import is performed. Any reference module records created during import, are not deleted.

![](successmessageImport.png?width=100%)

If the record limit has crossed 'Immediate Import Threshold' count, then the import is scheduled and the following message is shown:

![](importscheduled.png?width=100%)

Once the scheduled Import is completed, an email notification is sent to the user who scheduled the Import along with the Import Result.

Understanding error messages
----------------------------

### Data Corruption Error

![](importerror.png?width=100%)

This error shows up when the import has been interrupted for various reasons like crashed in between or canceled by a user etc. This error indicates that the import table still has records to be imported into the system, but all the information related to the import (like mapping, default values, merge criteria) are all lost. So these records can not be imported and the user needs to clear this data before starting any other import.

### Import Locked Error

![](importlocked.png?width=100%)

This error indicates that the Import on the module that user is trying to import, has been locked by another user's import. The details of the module, user and the time at which the Import has been locked, are exposed in the error message itself.

### Import Interrupted Error

![](errormessage.png?width=100%)


When a non-admin user triggers an import, and admin user tries to import to the same module, at the same time, admin user will not get Import locked error. Instead, admin user will be able to see the current status of the Import triggered by the non-admin user and will also be able to Cancel the import. In this case, when non-admin user is in the middle of the import and the admin user cancels the import, the error message above is shown to the non-admin user.

JSON File Format
--------------------------

The format of the JSON file is an array of objects that represent the records to be imported. The properties of the object are the names of the fields for the mapping.

```json
[
    {
        "Salutation": "--None--",
        "First Name": "Lina",
        "Contact No.": "CON1",
        "Last Name": "Schwiebert",
        "Office Phone": "03-3608-5660",
        "Organization Name": "Chemex Labs Ltd",
        "Mobile": "0487-835-113",
        "Lead Source": "Web Site",
        "Home Phone": "",
        "Title": "VP Supply Chain",
        "Other Phone": "",
        "Department": "Marketing",
        "Fax": "",
        "Email": "lina@yahoo.com",
        "Birthdate": "02-08-1992",
        "Assistant": "",
        "Reports To Contact": "",
        "Unique Identifier": "a609725772dc91ad733b19e4100cf68bb30195d1"
    },
    {
        "Salutation": "--None--",
        "First Name": "Julieta",
        "Contact No.": "CON2",
        "Last Name": "Cropsey",
        "Office Phone": "07-4217-6258",
        "Organization Name": "Atrium Marketing Inc",
        "Mobile": "0420-286-404",
        "Lead Source": "Self Generated",
        "Home Phone": "",
        "Title": "VP Supply Chain",
        "Other Phone": "",
        "Department": "Management",
        "Fax": "",
        "Email": "julieta@yahoo.com",
        "Birthdate": "07-12-1996",
        "Assistant": "",
        "Reports To Contact": "",
        "Unique Identifier": "d9692723137a4f119c900157b38189738e692fc4"
    }
]
```

Frequently Asked Questions
--------------------------

<div class="notices blue">
<h2>I think I have all the columns correctly formatted but when I import all the records are rejected. None are imported and I get no error message.</h2>
<hr>
Make sure all the date fields are in the same format as the user importing the data.
</div>
