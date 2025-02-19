---
title: 'Security Guide Examples'
metadata:
    description: 'Security Guide Examples'
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
        - security
        - manual
        - securityguide
    tag:
        - guide
        - example
---

This chapter explains on examples how role based security and the other security settings can be used to manage the CRM system.

## User Administration Basics

From the technical point of view, user administration means the
administration of permissions. Essentially, the use of role-based
security settings depends on the number of users and the company
structure. Few users in small enterprises have few requirements to a
permission administration. With an increasing number of users the
complexity of the relations between the users increases and usually it
develops the need to assign and administer individual user
permissions.

The CRM system offers a privilege system that is based on the following simple looking rules:

- Who can see certain data?
- Who can change certain data?
- Who can delete certain data?
- Who can create certain data?

At the CRM system permission assignment primarily means the withdrawal
of permissions. In the practical work with the CRM, this is most helpful
and necessary as the following examples illustrate:

- A selling coworker would feel it surely as unpleasant if somebody else changes the data of its customers without its knowledge.
- Personal information remains confidential only if other coworkers are not allowed to see those.
- The company management does not want that everybody can see the revenue numbers.
- Only one person is allowed to change the product or service catalog.
- It is not useful if any CRM user can see private information.

Therefore, it is necessary that the user permission assignment is truly based on business requirements as described in the following examples:

- Only the sales staff is allowed to change customer-related data.
- The secretary does not get any access to revenue numbers.
- Only the product manager is allowed to change prices of services or goods offered by the company.
- Only the management is allowed to see all CRM data.
- Nobody is allowed to export any contacts.

Considering the CRM system capabilities of managing user permissions you should configure your system in the following order:

1. Set the Default Global Access Privileges and Default Organization Fields Access
2. Create Profiles
3. Define Roles
4. Create Users
5. Create Groups if needed
6. Create Custom Access Privileges if needed

### Access Control for Single Users

Single users do not need any permission management. They have and need
all permissions to access and to change all data stored at the CRM.
Nevertheless, it is helpful to know the basics of role-based security
assignments. This might be needed if additional users will be required
in the future.

 ! Never use the "admin" role for your daily work with the CRM system. It is advised to create individual users instead. Later, if you want to delete a user, you can assign all data to a new user.

### Access Control for a small number of Users

A small number of users, who use the CRM system together, should be familiar with the simple solutions offered by the role-based security assignment. That includes especially:

- To prohibit that other CRM users see confidential data.
- To prohibit that other users can delete, modify or export data.

In a small organization, there is usually no pronounced hierarchy
between coworkers. A complex permission administration does not have to
be developed. However, if it should be necessary to granulate the
permissions more finely, you should begin with the use of profiles. Each
individual user may get its own role with a certain profile.

### Access Control for a higher number of Users

To provide a larger number of users within an organization with
different user rights, a clear structure of the permission assignment is
necessary. The CRM is powerful enough to mirror the job-related
permissions of most hierarchical structures of companies.

------------------------------------------------------------------------

[Next](examples) | Examples

------------------------------------------------------------------------

© 2006 crm-now
