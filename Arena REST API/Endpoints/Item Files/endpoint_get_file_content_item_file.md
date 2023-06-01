# GET Item File Content
/items/&lt;GUID&gt;/files/&lt;GUID&gt;/content

Returns file content belonging to a file with a given GUID, which is associated with an item with a given GUID.

## Request Header Body

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| arena_session_id<br> |   | unique ID for session obtained from login<br> |
| content-type<br> | application/json<br> |   |

## Response Codes

| Code<br> | Description<br> |
|  --- |  --- | 
| 200<br> | Success<br> |
| 400<br> | Failure<br> |

## Response Header

| Name<br> | Value<br> | Description<br> |
|  --- |  --- |  --- | 
| Content-Length<br> | number<br> | number of characters in response<br> |
| Content-Type<br> | determined by file<br> | content type of file<br> |
| Date<br> | date<br> | today's date and time<br> |
| Server<br> | ArenaSolutions<br> |   |
| X-Arena-Next-Request-Limit-Reset<br> | date<br> | the scheduled time for resetting of the count<br> |
| X-Arena-Requests-Remaining<br> | number<br> | how many calls left<br> |

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
* *If the file server is inaccessible, it may return a 400 status with no message.

