---
title: 'Login to Web Service'
---

Login to Web Service
====================

Access to the System
--------------------

You need a valid coreBOS user to access the webservice. All the
operations you can do through the REST interface will be limited by the
coreBOS permission system of the connected user.

The REST API does not use the users password to connect. Instead it
needs the user's access key which is a unique identifier created for
each user that can be found in the user's preferences page.

<img src="/en/devel/corebosws/accesskey.png" class="align-center" width="800" />

The login operation establishes a session between the REST client and
the coreBOS application, validates the user and returns a session
identifier which must be used in all subsequent calls to coreBOS.

This login process is done in two steps, first we ask coreBOS for a
challenge sequence and then we use the returned string to encode our
access key for the final validation.

### Get Challenge

<table>
<thead>
<tr class="header">
<th>Purpose:</th>
<th>get a challenge string to encode the password for login</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Profile:</td>
<td>getchallenge(username:String):GetChallengeResult</td>
</tr>
<tr class="even">
<td>Send Type:</td>
<td>GET</td>
</tr>
<tr class="odd">
<td>Parameters:</td>
<td>username: name of an active and valid user in coreBOS</td>
</tr>
<tr class="even">
<td>Returns:</td>
<td>A GetChallengeResult object with the challenge token and it's time to live<code>GetChallengeResult{
token:String //challenge string
serverTime:TimeStamp //time on server
expireTime:TimeStamp //expire time of token
}</code></td>
</tr>
<tr class="odd">
<td>URL Format:</td>
<td><code>http://corebos_url/webservice.php?operation=getchallenge&amp;username=[username]</code></td>
</tr>
</tbody>
</table>

### Login

Now that we have the challenge token we can proceed with the login step.
For this we have to send the user name and a verification string. This
verification string can be constructed in two ways:

      *as an md5 encrypted string of the challenge token plus the user's access key
      *as a concatenation of the token string plus the user's password <wrap em>this is insecure and NOT recommended</wrap>

This operation is executed as POST

<table>
<thead>
<tr class="header">
<th>Purpose:</th>
<th>Validate the user's access in the web service interface. The use of the getchallenge token is required</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Profile:</td>
<td>login(username:String, accessKey:String):LoginResult</td>
</tr>
<tr class="even">
<td>Send Type:</td>
<td>POST</td>
</tr>
<tr class="odd">
<td>Parameters:</td>
<td>username: name of the active coreBOS user that needs access<br />
accessKey: [token+password|md5(token+accesskey)]</td>
</tr>
<tr class="even">
<td>Returns:</td>
<td>A LoginResult object with the session identifier and some additional information<code>LoginResult{
sessionId:String //unique session identifier
userId:String //application user webserivce ID
version:String //Webservice interface version
vtigerVersion:String //coreBOS version
}</code></td>
</tr>
<tr class="odd">
<td>URL Format:</td>
<td><code>http://corebos_url/webservice.php?operation=login&amp;username=[username]&amp;accessKey=[accessKey]</code></td>
</tr>
<tr class="even">
<td>Comments:</td>
<td>The accessKey parameter is written with a capital 'K'<br />
The user's access key can be found on the user's profile screen inside the application</td>
</tr>
</tbody>
</table>

Once these two steps have been taken we can continue by calling any of
the web service functions.

### Logout

<table>
<thead>
<tr class="header">
<th>Method:</th>
<th>logout</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Purpose:</td>
<td>The logout service eliminates the session information, invalidating any further operations with that session ID. For security reasons this method should be called when the user of the external application finishes his tasks. He should have an option to close the application.</td>
</tr>
<tr class="even">
<td>Profile:</td>
<td>logout(sessionId:string):Map</td>
</tr>
<tr class="odd">
<td>Send as:</td>
<td>POST</td>
</tr>
<tr class="even">
<td>Parameters:</td>
<td>=&gt; sessionId: session ID to invalidate.</td>
</tr>
<tr class="odd">
<td>Response:</td>
<td>map with one entry: successfull</td>
</tr>
</tbody>
</table>

### More Information

-   This method of authentication is called Challenge-Handshake
    Authentication Protocol and it is more secure than a
    username/password authentication. [Read here for more
    information](https://tools.ietf.org/html/rfc1994)
-   [Read here for methods on how to change the user password and/or
    access key](/en/devel/corebosws/methodreference#crud_users)

------------------------------------------------------------------------

&lt;WRAP right&gt; [Next: Query
language](/en/devel/corebosws/querylanguage) | [Table of
Contents](/en/devel/corebosws/tableofcontents) &lt;/WRAP&gt;

------------------------------------------------------------------------
