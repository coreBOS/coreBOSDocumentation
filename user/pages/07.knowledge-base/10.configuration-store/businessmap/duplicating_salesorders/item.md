<div class="code-toolbar">
<pre class=" language-xml" tabindex="0">
<code class="language-xml hljs">
&lt;map&gt;
&lt;originmodule&gt;
  &lt;originname&gt;SalesOrder&lt;/originname&gt;
&lt;/originmodule&gt;
&lt;targetmodule&gt;
  &lt;targetname&gt;SalesOrder&lt;/targetname&gt;
&lt;/targetmodule&gt;
&lt;fields&gt;
  &lt;field&gt;
    &lt;fieldname&gt;sostatus&lt;/fieldname&gt;
    &lt;Orgfields&gt;
      &lt;Orgfield&gt;
        &lt;OrgfieldName&gt;Created&lt;/OrgfieldName&gt; { Set the status to "Created" regardless of the source SO }
        &lt;OrgfieldID&gt;CONST&lt;/OrgfieldID&gt;
      &lt;/Orgfield&gt;
     &lt;/Orgfields&gt;
  &lt;/field&gt;
  &lt;field&gt;
    &lt;fieldname&gt;ship_street&lt;/fieldname&gt;
    &lt;Orgfields&gt;
      &lt;Orgfield&gt;
        &lt;OrgfieldName&gt;$(account_id : (Accounts) ship_street)&lt;/OrgfieldName&gt;
        &lt;OrgfieldID&gt;FIELD&lt;/OrgfieldID&gt;
      &lt;/Orgfield&gt;
     &lt;/Orgfields&gt;
  &lt;/field&gt;
  &lt;field&gt;
    &lt;fieldname&gt;bill_street&lt;/fieldname&gt;
    &lt;Orgfields&gt;
      &lt;Orgfield&gt;
        &lt;OrgfieldName&gt;$(account_id : (Accounts) bill_street)&lt;/OrgfieldName&gt;
        &lt;OrgfieldID&gt;FIELD&lt;/OrgfieldID&gt;
      &lt;/Orgfield&gt;
     &lt;/Orgfields&gt;
  &lt;/field&gt;
  &lt;field&gt;
    &lt;fieldname&gt;bill_city&lt;/fieldname&gt;
    &lt;Orgfields&gt;
      &lt;Orgfield&gt;
        &lt;OrgfieldName&gt;$(account_id : (Accounts) bill_city)&lt;/OrgfieldName&gt;
        &lt;OrgfieldID&gt;FIELD&lt;/OrgfieldID&gt;
      &lt;/Orgfield&gt;
     &lt;/Orgfields&gt;
  &lt;/field&gt;
  &lt;field&gt;
    &lt;fieldname&gt;ship_city&lt;/fieldname&gt;
    &lt;Orgfields&gt;
      &lt;Orgfield&gt;
        &lt;OrgfieldName&gt;$(account_id : (Accounts) ship_city)&lt;/OrgfieldName&gt;
        &lt;OrgfieldID&gt;FIELD&lt;/OrgfieldID&gt;
      &lt;/Orgfield&gt;
     &lt;/Orgfields&gt;
  &lt;/field&gt;
  &lt;field&gt;
    &lt;fieldname&gt;bill_code&lt;/fieldname&gt;
    &lt;Orgfields&gt;
      &lt;Orgfield&gt;
        &lt;OrgfieldName&gt;$(account_id : (Accounts) bill_code)&lt;/OrgfieldName&gt;
        &lt;OrgfieldID&gt;FIELD&lt;/OrgfieldID&gt;
      &lt;/Orgfield&gt;
     &lt;/Orgfields&gt;
  &lt;/field&gt;
  &lt;field&gt;
    &lt;fieldname&gt;ship_code&lt;/fieldname&gt;
    &lt;Orgfields&gt;
      &lt;Orgfield&gt;
        &lt;OrgfieldName&gt;$(account_id : (Accounts) ship_code)&lt;/OrgfieldName&gt;
        &lt;OrgfieldID&gt;FIELD&lt;/OrgfieldID&gt;
      &lt;/Orgfield&gt;
     &lt;/Orgfields&gt;
  &lt;/field&gt;
  &lt;field&gt;
    &lt;fieldname&gt;ship_country&lt;/fieldname&gt;
    &lt;Orgfields&gt;
      &lt;Orgfield&gt;
        &lt;OrgfieldName&gt;$(account_id : (Accounts) ship_country)&lt;/OrgfieldName&gt;
        &lt;OrgfieldID&gt;FIELD&lt;/OrgfieldID&gt;
      &lt;/Orgfield&gt;
     &lt;/Orgfields&gt;
  &lt;/field&gt;
  &lt;field&gt;
    &lt;fieldname&gt;bill_country&lt;/fieldname&gt;
    &lt;Orgfields&gt;
      &lt;Orgfield&gt;
        &lt;OrgfieldName&gt;$(account_id : (Accounts) bill_country)&lt;/OrgfieldName&gt;
        &lt;OrgfieldID&gt;FIELD&lt;/OrgfieldID&gt;
      &lt;/Orgfield&gt;
     &lt;/Orgfields&gt;
  &lt;/field&gt;
&lt;/fields&gt;
&lt;/map&gt;
</code></pre>
<div class="toolbar">
	<div class="toolbar-item"><span>XML</span></div>
	<div class="toolbar-item"><button>Copy</button></div>
</div>
</div>