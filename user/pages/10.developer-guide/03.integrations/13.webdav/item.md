---
title: 'Integration with Sabre/DAV WebDAV'
---

Integration with Sabre/DAV WebDAV
---------------------------------

[Wikipedia Definition](https://en.wikipedia.org/wiki/WebDAV)

[Blog Post Presentation](https://blog.corebos.org/blog/webdav)

### Configuration

-   Activate Rewrite module in apache web server. Note, this integration
    does not work without Apache.
-   Activate the service by setting the **WEBDAV\_Enabled** global
    variable to 1 for those users that you want to give access to.
-   They will have to access the URL:
    <https://your_server/your_corebos/webdav>
-   They will have to use their username and access key to be granted
    access
-   Enjoy

### Mount Filesystem command

    sudo mount.davfs http://localhost/coreBOSTest/webdav webdav -o rw,uid=joe
