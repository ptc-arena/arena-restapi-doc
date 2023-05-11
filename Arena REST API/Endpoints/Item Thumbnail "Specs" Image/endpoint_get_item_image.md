# GET Item Thumbnail Image Content


GET /items/&lt;GUID&gt;/image/content

Returns the Item Thumbnail Image content with a given Item GUID. The Item Thumbnail Image \(also known as the Specs Image\) is located within the Specs view of an Item.

## Request Header Body

| Name | Value | Description |
|  --- |  --- |  --- | 
| arena_session_id |   | unique ID for session obtained from login |
| content\-type | application/json |   |

## Response Codes

| Code | Description |
|  --- |  --- | 
| 200 | Success |
| 400 | Failure |

## Response Header

| Name | Value | Description |
|  --- |  --- |  --- | 
| Content\-Length | number | number of characters in response |
| Content\-Type | determined by file  | content type of file |
| Date | date | today's date and time |
| Server | ArenaSolutions |   |
| X\-Arena\-Next\-Request\-Limit\-Reset  | date | the scheduled time for resetting of the count |
| X\-Arena\-Requests\-Remaining  | number | how many calls left |

## Sample Response Body
No JSON response. Returns the content of the File as an Input Stream.

An error is returned if:

* the GUID is not valid.

```
{
  "status": 400,
  "errors": [
    {
      "code": 3011,
      "message": "The guid \"XFWQ0GZGZDJ015J12\" is not valid."
    }
  ]
}
```
* An error is thrown by the file server

```
{
  "status": 400,
  "errors": [
    {
      "code": 3017,
      "message": "The file with guid \"7P60AQ9P8RAS7F6J\" cannot be downloaded at this time."
    }
  ]
}
```
* \*If the file server is inaccessible, it may return a 400 status with no message.

