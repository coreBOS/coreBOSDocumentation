---
title: 'Extend Session and Logout'
---

Extend Session and Logout
-------------------------

The extend session service permits us to access the web service API from
within coreBOS itself. If the user has already validated his session in
the application we can use that information to log in to the web service
API and execute commands as if we were connecting from outside the
application. It is worth noting that both sessions become dependent so
if the user logs out of either he will automatically be logged out of
the other connection.

<table>
<thead>
<tr class="header">
<th>Method:</th>
<th>extendsession</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Purpose:</td>
<td>When a user has already logged in and has an active session, it is useful to be able to use that same session to access the web service API without forcing the user to log in again. This method will detect the existing session and return a validated login session for the web service API</td>
</tr>
<tr class="even">
<td>Profile:</td>
<td>extendsession():Map</td>
</tr>
<tr class="odd">
<td>Send as:</td>
<td>POST</td>
</tr>
<tr class="even">
<td>Parameters:</td>
<td></td>
</tr>
<tr class="odd">
<td>Response:</td>
<td>A map which contains these fields:<br />
=&gt; sessionName: validated session ID to use in subsequent calls<br />
=&gt; userId: web service ID of the connected user<br />
=&gt; version: coreBOS and web service version numbers</td>
</tr>
</tbody>
</table>

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

------------------------------------------------------------------------

&lt;WRAP right&gt; [Next: Add web service end
points](/en/devel/corebosws/manual/addws) | [Table of
Contents](/en/devel/corebosws/tableofcontents) &lt;/WRAP&gt;

------------------------------------------------------------------------
