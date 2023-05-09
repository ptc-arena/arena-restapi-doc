# GET Individual File Association for an Item


/items/&lt;GUID&gt;/files/&lt;GUID&gt;

Returns a  object with a given GUID belonging to an item with a given GUID. 

## Sample Responses
Success \- 200

```
{
    "creationDateTime": null,
    "file": {
      "author": {
        "fullName": "Alan Goodrich"
      },
      "category": {
        "guid": "BTCVEXGQ9S4C0T0Q"
      },
      "corrected": false,
      "creationDateTime": "2014-02-13T22:50:13Z",
      "description": null,
      "edition": "1",
      "format": "txt",
      "guid": "EWGZ4UVV4BUATC3S55N1",
      "hasMarkup":false,
      "lastModifiedDateTime": "2014-02-13T22:50:13Z",
      "latest":true,
      "location": null,
      "mimeType": null,
      "name": "test file.txt",
      "number": "FILE-000972",
      "private":false,
      "size": 35,
      "storageMethod": 0,
      "title": "test file"
    },
    "guid": "N5O7Q9SYH0W5SPPV",
    "primary":false
}

```
An error is returned if:

* the GUID is not valid.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3011,
         "message":"The guid \"XFWQ0GZGZDJ015J12\" is not valid."
      }
   ]
}
```
* the file does not exist.

```
{  
   "status":400,
   "errors":[  
      {  
         "code":3029,
         "message":"The file association does not exist between object \"7P9SBJQCS0J0JX3FQYB1\" and object \"P7RAT18UAI1H0J2BCXIP\"."
      }
   ]
}
```
