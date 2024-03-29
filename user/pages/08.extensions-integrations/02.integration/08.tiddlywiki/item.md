---
title: 'Integration with TiddlyWiki'
metadata:
    description: 'Allows anyone to create personal self contained hypertext documents that can be posted to a web server'
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
        - integration
    tag:
        - tiddlywiki
---

<strong> [TiddlyWiki](https://tiddlywiki.com/) </strong>

We have two ways of using TiddlyWiki with coreBOS: with WebDAV and with a native plugin.

The goal of the integration is to use coreBOS as a backend to save the
tiddlers. In other words, since TiddlyWiki does not save the wiki
entries that you create, we need a way to persist them. TiddlyWiki has
various methods to do that and this integration adds another one where
you can save your wiki entries to coreBOS.

### Using WebDAV

One of the methods that TiddlyWiki offers to save the work you do is to
save the whole file to a WebDAV server.

This is really easy to implement. You configure your web server (apache,
for example) to serve a directory as WebDAV, you copy your TiddlyWiki
file to that directory, and access the file in the browser. TiddlyWiki
will automatically notice that it is in a WebDAV directory and save the
whole file every time you click on the Save button.

All that is left to do is make sure that you make backups of that
directory.

Another option is to use the [coreBOS native WebDAV integration](../10.webdav). This functionality will enable
WebDAV access to the Document module. So you will be able to upload your
TiddlyWiki file to a Document record in coreBOS and then access this
document through the WebDAV browser UI. Once you click on the TiddlyWiki
file it will open and see that it is on a WebDAV server, so it will save
the wiki in the document record every time you click on the Save button.

There is one step you need to do in order to get this working. coreBOS
does not permit uploading HTML files. For security reasons it changes
the extension to .txt to avoid (or reduce) the possibility of unwanted
execution of malicious code.

Since TiddlyWiki is an HTML file we have to make a change to permit
saving this type of file. Edit your config.inc.php file and look for the
$upload_badext variable. You must eliminate the "HTML" entry from that
array.

### Using TiddlyWiki Plugin

We have created a plugin for TiddlyWiki that you can install like all the other plugins.

This plugin will permit you to log in to your coreBOS. Once you are logged in, the plugin will access your existing wiki entries from the Conversation module and load them into the TiddlyWiki instance as if they had been saved in the file. From that point on, the wiki entries you create or modify will be saved back in the Conversation module.

### Comparision and Comments

With the WebDAV solution, the whole wiki is saved in one big file,
either in the WebDAV directory you setup or in the coreBOS Document
record, so you can't search inside those wiki entries.

Using the plugin, since each tiddler is saved in an independent record
you will be able to use coreBOS mechanisms to search and manage them
also.

------------------------------------------------------------------------

[Next](../09.typeform) | Chapter 9: Typeform Configuration

------------------------------------------------------------------------