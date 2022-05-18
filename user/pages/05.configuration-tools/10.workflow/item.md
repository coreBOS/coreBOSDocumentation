---
title: 'Workflows'
metadata:
    description: 'Types of Workflows'
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
        - adminmanuals
        - workflows
    tag:
        - workflows
        
---

Workflows are a very powerful part of the application. They permit us to automate our business logic to some extent making it possible to standardize process and have the application do some of the repetitive tasks our business requires.

It is necessary to execute four steps to configure and setup a workflow:

-   Select a module against which the workflow will be executed and give it a name
-   Select when the workflow will be triggered
-   Select any conditions that restrict for what records the workflow must take it's actions
-   Define and configure the different tasks that the workflow will perform


In the next sections you will be able to find more information on these steps.

[-  Workflow launch conditions](http://localhost/coreBOSDocumentation/configuration-tools/workflow/workflow_launch_conditions) <br>
[-  Workflow step by step explanation](http://localhost/coreBOSDocumentation/configuration-tools/workflow/workflow_stepbystep) <br>
[-  Scheduled Time based Workflows](http://localhost/coreBOSDocumentation/configuration-tools/workflow/scheduled_workflows) <br>
[-  Workflow conditions](http://localhost/coreBOSDocumentation/configuration-tools/workflow/workflow_conditions) <br>

## Workflow Tasks

[-  Update Workflow Tasks](http://localhost/coreBOSDocumentation/configuration-tools/workflow/update_workflows) <br>
[-  Upsert Workflow Task](http://localhost/coreBOSDocumentation/configuration-tools/workflow/upsert_workflows) <br>
[-  Add/Delete Tags Workflow Tasks](http://localhost/coreBOSDocumentation/configuration-tools/workflow/addeltag_workflows) <br>
[-  Related Product/Service Workflow Task](http://localhost/coreBOSDocumentation/configuration-tools/workflow/relateproductservice_workflows) <br>
[-  Invoke Custom Functions Workflow Tasks](http://localhost/coreBOSDocumentation/configuration-tools/workflow/invokecustomfunction_workflows) <br>
[-  SMS Workflow Tasks](http://localhost/coreBOSDocumentation/others/smsnotifier#sms-task-with-work-flow) <br>

## Workflow Examples

[-  Workflow Examples](http://localhost/coreBOSDocumentation/configuration-tools/workflow/workflow_examples) <br>
[-  How to send emails/sms on specific week days](http://localhost/coreBOSDocumentation/configuration-tools/workflow/workflow_weekendwarning) <br>
[-  Workflow tricks and tips](http://localhost/coreBOSDocumentation/configuration-tools/workflow/workflow_tricksandtips) <br>
