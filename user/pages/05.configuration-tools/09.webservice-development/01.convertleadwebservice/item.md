---
title: 'Convert Lead Webservice'
---

Convert Lead Webservice
=======================

Usage example of convert lead web service in order to convert an
existing Leads into Accounts, Contacts & Opportunity using Webservice.

Important points to note before using the following code:

-   Check table vtiger\_ws\_entity to know the "id" (Webservice module
    ID) of the "Leads" module. Ensure that the Lead ID passed to
    vtws\_convertleads function is in 'x' format.

<!-- -->

-   Following example uses standard vtwsclib library.
-   Sample code:`<?php
    include_once('vtwsclib/Vtiger/WSClient.php');

    function vtws_login(){
            $$url = 'http://en.vtiger.com/wip';
        $client = new Vtiger_WSClient($url);
        $login = $client->doLogin('admin', 'KpS9EjNz16JtPmoe');
            if(!$login) return 0;
            return $client;
    }

    function vtws_convertleads($recordid){
            $client = vtws_login();
            if ($client <> 0){
                    $recordInfo = $client->doRetrieve($recordid);
                    $wasError= $client->lastError();
                    if($wasError) {
                            return $wasError['code'] . ':' . $wasError['message'];
                    }
                    if($recordInfo) {
                            $client1 = vtws_login();
                            $convert_lead_array = array();
                            $convert_lead_array['leadId'] = $recordInfo['id'];
                            $convert_lead_array['assignedTo'] = $recordInfo['assigned_user_id'];
                            $convert_lead_array['entities']['Accounts']['create']=true;
                            $convert_lead_array['entities']['Accounts']['name']='Accounts';
                            $convert_lead_array['entities']['Accounts']['accountname'] = $recordInfo['company'];
                            $convert_lead_array['entities']['Accounts']['industry']=$recordInfo['industry'];
                            $convert_lead_array['entities']['Potentials']['create']=true;
                            $convert_lead_array['entities']['Potentials']['name']='Potentials';
                            $convert_lead_array['entities']['Potentials']['potentialname']=$recordInfo['company'];
                            $convert_lead_array['entities']['Potentials']['closingdate']= date("Y-m-d", strtotime("+1 week Saturday"));
                            $convert_lead_array['entities']['Potentials']['sales_stage']= 'Prospecting';
                            $convert_lead_array['entities']['Potentials']['amount']= 0;
                            $convert_lead_array['entities']['Contacts']['create']=true;
                            $convert_lead_array['entities']['Contacts']['name']='Contacts';
                            $convert_lead_array['entities']['Contacts']['lastname']=$recordInfo['lastname'];
                            $convert_lead_array['entities']['Contacts']['firstname']=$recordInfo['firstname'];
                            $convert_lead_array['entities']['Contacts']['email']=$recordInfo['email'];
                            $convert_lead_json = json_encode($convert_lead_array);
                            $response = $client1->doInvoke('convertlead', array('element'=>$convert_lead_json));
                            $wasError = $client1->lastError();
                            if($wasError) {
                                    return $wasError['code'] . ':' . $wasError['message'];
                            } else {
                                    return 1;
                            }
                    }
            }else{
                    return 'Login failed';
            }
    }

    $d = '2x21022';
    echo vtws_convertleads($d);

    ?>`

<table>
<thead>
<tr class="header">
<th>Purpose:</th>
<th>Permits the conversion of a lead into an account, contact and potential. This service is used by the application itself when converting leads.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Profile:</td>
<td>convertlead($entityvalues): Map</td>
</tr>
<tr class="even">
<td>Send as:</td>
<td>POST</td>
</tr>
<tr class="odd">
<td>Parameters:</td>
<td>&lt;code&gt; id: $entityvalues is an array. Consult the modules/Leads/LeadConvertToEntities.php to see an example.&lt;/code&gt;</td>
</tr>
<tr class="even">
<td>Returns:</td>
<td>Array with all the information of the new objects created</td>
</tr>
<tr class="odd">
<td>URL Format:</td>
<td><code>http://vtiger_url/webservice.php?operation=deleteUser&amp;sessionName=[session id]</code></td>
</tr>
</tbody>
</table>

[Thanks
Ashutosh](https://discussions.vtiger.com/index.php?p=/discussion/166499/usage-example-of-convert-lead-webservice)

&lt;WRAP center round info 90%&gt; You can also find an [example in the
coreBOS Webservice
development](https://github.com/tsolucio/coreBOSwsDevelopment/blob/master/testcode/470_convertLead.php)
tool. &lt;/WRAP&gt;

&lt;WRAP center round info 90%&gt; By setting
$convert\_lead\_array\['entities'\]\[<span
class="underline">Contacts|Accounts|Potential</span>\]\['create'\] to
**false** you can avoid creating a record in that module. &lt;/WRAP&gt;

&lt;WRAP center round info 90%&gt; By default, a Lead is Converted into
a Contact, but you can indicate the module you want to have the Lead
values transferred to using the variable ***transferRelatedRecordsTo***

$convert\_lead\_array\['entities'\]\['transferRelatedRecordsTo'\] =
'Accounts';

If you indicate that no Contact should be created the Lead values will
be transferred to the Account.

If you indicate that neither a Contact nor an Account should be created
the process will fail with a web service exception.

&lt;/WRAP&gt;

&lt;WRAP center round info 90%&gt; By default, the process will search
for an existing Account with the same company name and relate the new
records with this Account. This is done to avoid duplicates. You can
override this behavior by assigning a value to the meta-variable
***forcecreate*** like this:

$convert\_lead\_array\['entities'\]\[Accounts\]\['forcecreate'\] = true;

Be careful as this will easily create duplicate account names and you
won't be able to edit them unless you set the global variable
***Accounts\_BlockDuplicateName*** to false. &lt;/WRAP&gt;

------------------------------------------------------------------------

&lt;WRAP right&gt; [Next: Portal user
login](/en/devel/corebosws/portallogin) | [Table of
Contents](/en/devel/corebosws/tableofcontents) &lt;/WRAP&gt;

------------------------------------------------------------------------
