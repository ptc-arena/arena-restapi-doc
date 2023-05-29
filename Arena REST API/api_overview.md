# Overview
The Arena REST API \(Application Programming Interface\) allows you to programmatically exchange data with your workspaces. This documentation includes details about requests and responses from Arena servers, and instructs developers in how to construct requests. This documentation assumes some familiarity with APIs in general.

The table below details specific capabilties of the API.


|   | Search<br> | Create<br> | Read<br> | Update<br> | Delete<br> |
|  --- |  --- |  --- |  --- |  --- |  --- | 
| Item Summary Records<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| Item BOM Lines<br> | N/A<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| Item Source Relationships<br> | N/A<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| Item Revisions<br> | N/A<br> | ✔\*<br> | ✔<br> | N/A<br> | N/A<br> |
| Item Files Associations<br> | N/A<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| Item Compliance Requirements<br> | N/A<br> | ✔<br> | ✔<br> | ✔<br> | \-<br> |
| Item Where Used<br> | N/A<br> | N/A<br> | ✔<br> | N/A<br> | N/A<br> |
| Item Lifecycle<br> |   | ✔<br> |   |   |   |
| Item Export<br> | ✔<br> | ✔<br> | ✔<br> | N/A<br> | N/A<br> |
| Change Summary Records<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| Change Affected Items<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| Supplier Profile<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| Supplier Quality<br> |   |   | ✔<br> |   |   |
| Supplier Item Summary<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| Supplier Item File Associations<br> | N/A<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| Supplier Item Compliance Requirements<br> | N/A<br> | ✔<br> | ✔<br> | ✔<br> | \-<br> |
| Supplier Item Sourcing<br> |   |   | ✔<br> |   |   |
| File Records<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| File Editions<br> |   | ✔<br> | ✔<br> |   |   |
| File Associations<br> |   |   | ✔<br> |   |   |
| Quality Process Summary<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| Quality Process Details<br> | N/A<br> | \-<br> | ✔<br> | \-<br> | \-<br> |
| Quality Process Step/Affected Objects<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> | ✔<br> |
| DataExtract<br> |   | ✔<br> |   |   |   |
| Outbound Integrations<br> | ✔<br> |   | ✔<br> | ✔<br> |   |
| Recent Activity<br> |   | ✔<br> |   |   |   |

NOTES

\* Item Revisions are created using the items/lifecyclephasechanges endpoint.

