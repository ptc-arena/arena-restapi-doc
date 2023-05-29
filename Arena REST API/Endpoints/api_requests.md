# API Requests
The Arena REST API provides methods for accessing a resource, such as an Item or a category of Item, at a canonical URL. You can then perform an action upon that resource by specifying an endpoint URL, such as



 https://api.arenasolutions.com/&lt;version&gt;/items/&lt;item_GUID&gt;/revisions

which returns all revisions for a given Item resource. Note that the version takes the format e.g. v1 \(no decimal places\). The API version does not necessarily change with Arena releases.


The header of all requests must include:

* an access token "arena_session_id" for user authentication \(except Log In, which grants a token\)

* a content type declaration \("application/json", except for  file POST endpoints with content, where the file metadata is JSON and the file payload itself is "multipart/form\-data"\)

* an HTTP method declaration \(GET, POST, PUT, DELETE\)


Requests must be sent uncompressed. Responses may be returned uncompressed or compressed using gzip encoding.

