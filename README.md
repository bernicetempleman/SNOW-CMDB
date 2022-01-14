# SNOW-CMDB

## These are notes from researching CMDB:
CMDB, CI, CI Classes & CI Relationships

## CMDB is a Configuration Management Database
- A CMDB is primarily a data repository,
- CMD is used to store information describing configuration items, or CIs, as well as some asset-related information. 
- The CMDB also contains the relationships between CIs.
- video: https://youtu.be/qdEIYjs-Y3A

## Benefits of CMDB
- At its core, one of the most significant benefits of CMDB is that it takes all the siloed data across the enterprise required to run IT , and it brings it all together in a single place giving IT Operations visibility into all the IT resources in the enterprise. 
- It prevents data from being scattered across multiple different locations. 
- A CMDB helps IT teams in a number of ways, here are just a few:
- it helps eliminate outages,
- significantly reduce the time it takes to remediate an outage, 
remain in compliance, 
- avoid security and audit fines,
- understand important service contexts when making decisions, 
- which benefits risk assessment and reporting, and track software license and cloud costs
### Planning
- CMDB helps technology managers plan at both a detailed level with asset management and at a high level with enterprise architecture.
### Operating
- Core ITSM practices are improved by CMDB, including incident, change, and problem management.
- CMDB can improve risk assessment in change management by anticipating which systems and users might be impacted the most. It also aids compliance by helping teams manage audit trails and controls.
- CMDB affects incident management by identifying the changes and root causes of an incident, and moving toward a faster resolution. Incident records are associated with their CIs, which helps teams track incidents over time in conjunction with the assets impacted by the incident.
- Problem management benefits from CMDB in that it helps with root-cause analysis, which helps teams get to the source of a problem more quickly. It also supports proactive management by assisting teams with identifying assets that are in need of an upgrade to reduce service costs and downtime.
### Accounting
- It’s important to have application and service codes in IT finance, as it helps allocate billing statements and manage other finances.

## CMDB record types
###  Configuration Item (CI)
 -  Any computer, device, or service in the CMDB. 
-   A CI's record includes all of the relevant data, such as manufacturer, vendor, location, etc. 
-   Configuration items can be created or maintained either using tables,
  lists, and forms within the platform, or using
  the Discovery application.
  
###  Relation Type
  
-   A defined relationship between a CI and either another CI, a user, or
  a group. 

-   Relation types are defined twice, once from the perspective of the
  child CI and once from the parent CI's perspective. 

-   CMDB relationships can be established using Discovery or
  using the tables, lists, and forms within the platform. 

-   The CMDB form has a specific Related Items toolbar optimized for
  modifying relationships. 
 
## What is a CI
### Configuration Item
- A CI is a uniquely identified component used to deliver a service for which changes are controlled.
-  A CI can be :
 a physical entity (like a server),
 a logical entity (like an application), or
 an operational construct (like a cluster of servers).
 
 ## CMDB Classifications
-  CMDB classifications are groups of configuration items (CIs) that share attributes and are stored in their own table. 
- Classifications allow administrators to define the hierarchy of CIs within the CMDB. 
- A CI class refers to the actual table name in the instance database. In that context, CI Type is a friendly name that a CI is known by, such as computer, router, or printer.
- As good practice, keep CI classifications as simple as possible.

## CI Class manager
- Use the CI Class Manager to create a CI class,
 to update identification and reconciliation rules,
 to display CI relationships, and
to configure CMDB health settings.
- Navigate to Configuration > CI Class Manager.

## CI Relationships
- The CMDB, in contrast to a static asset list, helps you track not only the configuration items (CIs) within your system, but also the relationships between those items.
- A relationship in the CMDB consists of two CIs and a relationship type:
- Parent CI
- Child CI
- Type of the relationship that links both CIs
- For example, in the [Server1] [Managed by] [Server2] relationship:
- Server1 is the child CI
- Server2 is the parent CI
- [Managed by] is the relationship type
- Most CIs in a CMDB have multiple relationships to other CIs, users, and groups.
- The relationships between CIs can be automatically discovered.
-  If you use Discovery, many relationships can be automatically loaded into the system through the discovery process.
-  If you import your data from another system, you get some form of relationships.
- You can add to automatically discovered relationships, create relationships, or edit relationships for a CI by launching the CI relationship editor from the CI form.

## Dependent and Non-dependent relationships
Non-dependent relationships are not used for CI identification,
 and therefore can be deleted if no longer needed. 

### Dependent relationships are used for CI identification.
 Therefore they should not be directly deleted and they are not tracked.

- Information in the Relationship Sources [sys_rel_source] table can be used to decide if it is safe to delete a non-dependent relationship. For example, a discovery source which is attempting to delete a non-dependent relationship can confirm that:
- There are no other data sources for that relationship.
- The relationship was not updated for some specified length of time and therefore is no longer needed.
- When a non-dependent relationship is deleted from the CI Relationship [cmdb_rel_ci] table, all cascading corresponding records in - the Relationship Sources [sys_rel_source] table are deleted.

## Suggested class relationships
relationship types that are appropriate for a CI type, based on its class. 
- You can manage suggested relationships by navigating to Configuration > Suggested Relationships, or in the CI Class Manager.
- Add a suggested relationship
- Add a suggested relationship for a class. The list of suggested relationships for a class is available when you create a new relationship for a CI of that class.
- Relationship governance rules
- Relationship governance rules is a set of relationship rules used to ensure consistency and validity in modeling relationships between configuration items (CIs) in the CMDB. 
- Use relationship governance rules to prevent the selection of relationship types or directions that are not allowed between specific CI types.
- CI relations formatter
- The default CI form includes a CI relations formatter from which you can examine a CI and its relationships in various views. From the CI relations formatter, you can also launch the CI relationship editor for the CI.
- CI relationship editor
- Use the CI relationship editor to create CI relationships.
- Relation qualifier
- A relation qualifier, stores important information about the CI relationships.
- CI relationship security

# Configuration Module

## Multisource Report Builder
![image](https://user-images.githubusercontent.com/12488769/149430174-af9a91d9-6798-41d6-90d4-f54d4c285225.png)

## CI Class Manager
![image](https://user-images.githubusercontent.com/12488769/149430314-fea05b5d-dc75-4d39-9750-cb026624990e.png)

![image](https://user-images.githubusercontent.com/12488769/149430493-95ccc9e3-43e7-45d6-a997-d895f922b5d7.png)

## CMDB Groups

## CMDB Query Builder
![image](https://user-images.githubusercontent.com/12488769/149431414-9b851aad-57a9-42cc-b077-f3287929e7dc.png)

![image](https://user-images.githubusercontent.com/12488769/149431495-5ac02c01-d0ff-4ddb-840d-b5ce3ec7f656.png)

## Health Preference

## CMDB Remediations

## CMDB Reports

##  CMDB Data Manager

## Services
![image](https://user-images.githubusercontent.com/12488769/149432066-ada83873-6b37-4d62-83ac-07af619b68f4.png)

![image](https://user-images.githubusercontent.com/12488769/149432195-ef3ad562-f698-42bb-9e11-3ce7abb5e174.png)

## Service Offerings

## Exclusion list

##  Applications
![image](https://user-images.githubusercontent.com/12488769/149431784-bf733280-2a6f-46c6-8f39-fe476210c23c.png)

## Dynamic CI Groups

## CI Relationship Types
![image](https://user-images.githubusercontent.com/12488769/149432681-723fedfc-a88e-4f27-b4fc-082f74992496.png)


## CMDB_CI.list

![image](https://user-images.githubusercontent.com/12488769/147889681-bcb46a05-09e8-4879-8ce5-4cfc00666dc1.png)
