# Overview
The Arena REST API \(Application Programming Interface\) allows you to programmatically exchange data with your workspaces. This documentation includes details about requests and responses from Arena servers, and instructs developers in how to construct requests. This documentation assumes some familiarity with APIs in general.

The table below details specific capabilties of the API.


|   | Search  | Create  | Read  | Update  | Delete  |
|  --- |  --- |  --- |  --- |  --- |  --- | 
| Item Summary Records  | ✔  | ✔  | ✔  | ✔  | ✔  |
| Item BOM Lines  | N/A  | ✔  | ✔  | ✔  | ✔  |
| Item Source Relationships  | N/A  | ✔  | ✔  | ✔  | ✔  |
| Item Revisions  | N/A  | ✔\*  | ✔  | N/A  | N/A  |
| Item Files Associations  | N/A  | ✔  | ✔  | ✔  | ✔  |
| Item Compliance Requirements  | N/A  | ✔  | ✔  | ✔  | -  |
| Item Where Used  | N/A  | N/A  | ✔  | N/A  | N/A  |
| Item Lifecycle  |   | ✔  |   |   |   |
| Item Export  | ✔  | ✔  | ✔  | N/A  | N/A  |
| Change Summary Records  | ✔  | ✔  | ✔  | ✔  | ✔  |
| Change Affected Items  | ✔  | ✔  | ✔  | ✔  | ✔  |
| Supplier Profile  | ✔  | ✔  | ✔  | ✔  | ✔  |
| Supplier Quality  |   |   | ✔  |   |   |
| Supplier Item Summary  | ✔  | ✔  | ✔  | ✔  | ✔  |
| Supplier Item File Associations  | N/A  | ✔  | ✔  | ✔  | ✔  |
| Supplier Item Compliance Requirements  | N/A  | ✔  | ✔  | ✔  | -  |
| Supplier Item Sourcing  |   |   | ✔  |   |   |
| File Records  | ✔  | ✔  | ✔  | ✔  | ✔  |
| File Editions  |   | ✔  | ✔  |   |   |
| File Associations  |   |   | ✔  |   |   |
| Quality Process Summary  | ✔  | ✔  | ✔  | ✔  | ✔  |
| Quality Process Details  | N/A  | -  | ✔  | -  | -  |
| Quality Process Step/Affected Objects  | ✔  | ✔  | ✔  | ✔  | ✔  |
| DataExtract  |   | ✔  |   |   |   |
| Outbound Integrations  | ✔  |   | ✔  | ✔  |   |
| Recent Activity  |   | ✔  |   |   |   |

NOTES

\* Item Revisions are created using the items/lifecyclephasechanges endpoint.

