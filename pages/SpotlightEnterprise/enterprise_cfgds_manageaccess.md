---
title: Manage access to Spotlight connections
summary: "Define which Spotlight users are entitled to view which Spotlight connections."
sidebar: p_enterprise_sidebar
permalink: enterprise_cfgds_manageaccess.html
id: 712
folder: SpotlightEnterprise
---


Users who are members of the Spotlight Diagnostic Administrators group can use this screen to assign Spotlight users access privileges to Spotlight connections.

## Open this screen from the Spotlight Client

1. Click **Configure \| Diagnostic server**.
2. Select **Manage access to Spotlight connections**.

## Select the Diagnostic Server

In a federated environment you can select the Spotlight Diagnostic Server. Connections monitored under that Diagnostic Server will be listed.

## Spotlight Users and Spotlight Connections
Select a user from the left column of Spotlight Users. Spotlight connections are listed to the right. Each connection is set to on/off access for the selected Spotlight user. 

## Manage Access to Spotlight connections

Action on Manage Access to Spotlight connections | Administrator | User | Read-Only
-------------------------------------------------|---------------|------|----------
View all users | Yes | Yes | Yes
View all connections | Yes | Yes | Yes
View which connections are accessible by which users | Yes | Yes | Yes
Search user by username | Yes | Yes | Yes
Search connection by connection name, display name, connection type and tag | Yes | Yes | Yes
Deny the Administrator access to the connection | No | No | No
Allow/Deny connection to User or Read-Only user | Yes | No | No

{% include note.html content="All users are entitled to access all the connections(including newly added connections) until the Administrator explicitly denies it." %}


## Permission Precedence
Because an Active Directory user may also be included in Active Directory groups and a Spotlight user may have different roles configured, it is possible for conflicting permission settings to happen.

Here are some rules for resolving permissions conflicts:

1. "Administrator" role generally takes precedence over "Non Administrator" role.
2. "Deny" permissions generally take precedence over "Allow" permissions.

For more on Spotlight Diagnostic User Groups, see [Spotlight Diagnostic User Groups][enterprise_backend_spotlightdiagnosticusergroups].
For more on Manage access to Spotlight connections known issues, see [known issues configuring Spotlight][enterprise_releasenotes_knownissues].

{% include links.html %}
