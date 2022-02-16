<<<<<<< HEAD
---
title: 'Condition Expression Business Mapping'
---

=======
>>>>>>> d9a6103028e81b44714e2ad52b29f6d46ad9eb7b
Condition Expression Business Mapping
=====================================

This mapping permits us to evaluate an expression in the context of the
application and get the result to decide subsequent actions. It accepts
two formats, one is a direct expression from the workflow expression
engine and the other is a function expression that can be called from
inside the system. The function parameters will be changed to the
current record values if they exist.
<<<<<<< HEAD
```xml
     <map>
      <expression>uppercase('this string')</expression>
     </map>
```
```xml
     <map>
      <expression>accountname</expression>
     </map>
```
```xml
     <map>
      <expression>employees + 10</expression>
     </map>
```
```xml
     <map>
      <expression>if employees > 10 then 'true' else 'false' end</expression>
     </map>
```
```xml
=======

     <map>
      <expression>uppercase('this string')</expression>
     </map>

     <map>
      <expression>accountname</expression>
     </map>

     <map>
      <expression>employees + 10</expression>
     </map>

     <map>
      <expression>if employees > 10 then 'true' else 'false' end</expression>
     </map>

>>>>>>> d9a6103028e81b44714e2ad52b29f6d46ad9eb7b
    <map>
      <function>
       <name>isPermitted</name>
       <parameters>
        <parameter>Accounts</parameter>
        <parameter>CreateView</parameter>
        <parameter>record_id</parameter>
       </parameters>
      </function>
     </map>
<<<<<<< HEAD
```

the isPermitted mapping above will be converted into:

 ```
   isPermitted('Accounts','CreateView','74');
```
=======

the isPermitted mapping above will be converted into:

    isPermitted('Accounts','CreateView','74');
>>>>>>> d9a6103028e81b44714e2ad52b29f6d46ad9eb7b

Additional Information
----------------------

-   [Forum thread](http://discussions.corebos.org/thread-642.html)
