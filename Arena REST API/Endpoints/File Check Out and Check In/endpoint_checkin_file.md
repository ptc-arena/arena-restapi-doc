# POST File Check In


POST /files/checkoutstatuschanges

Only the user who checked out the File or an Account administrator can cancel the checkout.

The existing edition of the File  can not be checked in if the edition is locked \(for example it is associated with an effective item\).

A new edition of the File can be checked in even if the existing edition is locked. Only Files of storageMethod File can be checked in.

User must have a Full license to perform the File checkin. User must also have access to edit the File and full access to the File category.

## Request Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Sample Request Body - Creating a new edition. 


```
checkedOut: false
comment: check in the file
newEdition: true
file.author.fullName: Heidi Walker
file.category.guid: 3L507K5WJM5FYHW334R7
file.description: A design file
file.edition: 2
file.format": pdf
file.guid: K2M501MD03M2L47YKQ5B
file.private: false
file.storageMethodName: FILE
file.title: New Design File
file.content: [the physical file]
```
## Sample Request Body - Check In and edit the existing edition.


```
checkedOut: false
comment: check the file in
new edition: false
file.author.fullName: Heidi Walker
file.category.guid: 3L507K5WJM5FYHW334R7
file.description: A design file
file.edition: 2
file.format": pdf
file.guid: 2K4N1Y24FWFVEXN0XFLX
file.private: false
file.storageMethodName: FILE
file.title: New Design File
file.content: [the physical file]
```
## Response Codes

| Code | Description |
|  --- |  --- | 
| 201 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | determined by file type | content type of file |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-FileGuid | GUID string | GUID for new file \- only when including content |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Responses
No JSON response. 

* Response Header will contain the guid of the new file dition that was checked in.

* For File Check Ins where the existing edition is checked in, the response header will contain the guid of the existing file condition.

Request invalid if File is already checked in.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3133,
         "message":"The File cannot be updated."
      }
   ]
}
```
