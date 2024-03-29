---
title: 'Logging Stress test'
metadata:
    description: 'Logging Stress test'
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
        - sendemail
    tag:
        - debug
        - log
---

While working on coreBOS I ran into [this email](http://permalink.gmane.org/gmane.comp.web.vtigercrm.devel/5131) (which was ignored on the developers list) from Adam Heinz:

I reproduce it here as a reference:

```
 Adam Heinz | 6 Dec 21:44 2011    apache log4php 2.1.0

I recently noticed that log4php/LoggerManager.php has the comment /** Classes to avoid logging */.  This seems
a bit counterintuitive to me -- I would think it would be as simple as dialing down log levels in
log4php.properties, unless the underlying library is painfully slow.

I grabbed the latest tarball from http://logging.apache.org/log4php/download.html, dropped it into
include/log4php, deleted the old log4php and log4php.debug folders, and replaced include/logging.php with

require_once('config.php');
require_once('include/log4php/Logger.php');

include_once('config.performance.php');
global $PERFORMANCE_CONFIG;
if(isset($PERFORMANCE_CONFIG) && isset($PERFORMANCE_CONFIG['LOG4PHP_DEBUG']) && $PERFORMANCE_CONFIG['LOG4PHP_DEBUG']) {
	Logger::configure('log4php.debug.properties');
} else {
	Logger::configure('log4php.properties');
}

class LoggerManager {
	static function getlogger($name = 'ROOT') {
		return Logger::getLogger($name);
	}
}

I avoided s/LoggerManager/Logger/g for now, but that class is now easily deleted. I'm not seeing any
performance hit hammering my sandbox (virtual machine, 512MB, 1/4 Opteron CPU). I don't see any mailing list
archives -- would whoever had the original performance problems like to weigh in? I think this is the right
direction to take the code, but I don't have a load test environment.
```

The code above looked really correct (as most of Adam's changes did) but I needed to find out if we could really eliminate completely the mock up logging library, so I created a stress test script which now [can be found on github](https://github.com/tsolucio/corebos/blob/master/build/HelperScripts/stressTest.php) in the coreBOS project's build/HelperScripts directory.

This stress script creates 100 contacts in batches of 10, retrieves them and deletes them.

The table below shows the results. The conclusions are:

- Upgrading the library produced little difference which is good, besides the security bug fixes we may get some performance benefits on higher PHP versions
- There is a significant difference between the mock up library and the full logging library: we keep this structure and *config.performance.LOG4PHP\_DEBUG* **MUST** be set to false in production

```
    Stress Test         Php = 5.3                       
    Before upgrade      Log4php = 1.9           After upgrade       Log4php = 2.3       
    Log load    operation           Log load    operation       
    on  0,28    158,93          on  0,26    159,54      
    on  0,27    166,17          on  0,26    160,40      
    on  0,27    167,11          on  0,26    159,02      
    on  0,27    163,31          on  0,26    165,33      
    on  0,28    161,69          on  0,27    163,05      
    on  0,27    167,46          on  0,26    161,24      
    on  0,27    155,28          on  0,26    158,52      
    on  0,27    159,87          on  0,26    160,13      
    on  0,27    160,52          on  0,26    157,79      
    on  0,27    157,01  161,74      on  0,26    167,96  161,30  -0,44
                                        
    off 0,24    163,48          off 0,24    162,70      
    off 0,24    165,52          off 0,25    160,70      
    off 0,25    156,92          off 0,25    160,90      
    off 0,24    157,81          off 0,24    159,75      
    off 0,24    157,39          off 0,24    159,32      
    off 0,25    164,86          off 0,25    157,52      
    off 0,25    160,13          off 0,24    167,05      
    off 0,24    159,76          off 0,24    158,18      
    off 0,24    154,99          off 0,25    158,22      
    off 0,24    160,43  160,13      off 0,25    154,65  159,90  -0,23
                                        
                -1,61                   -1,40   
```