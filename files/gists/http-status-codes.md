Reference: RFC 2616 - HTTP Status Code Definitions
* [HTTP/1.1 Status Code Definitions](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html)
* [Additional HTTP Status Codes](http://tools.ietf.org/html/rfc6585)

### General
* 400 BAD REQUEST: The request was invalid or cannot be otherwise served. An accompanying error message will explain further. For security reasons, requests without authentication are considered invalid and will yield this response.
* 401 UNAUTHORIZED: The authentication credentials are missing, or if supplied are not valid or not sufficient to access the resource.
* 403 FORBIDDEN: The request has been refused. See the accompanying message for the specific reason (most likely for exceeding rate limit).
* 404 NOT FOUND: The URI requested is invalid or the resource requested does not exists.
* 406 NOT ACCEPTABLE: The request specified an invalid format.
* 410 GONE: This resource is gone. Used to indicate that an API endpoint has been turned off.
* 429 TOO MANY REQUESTS: Returned when a request cannot be served due to the application’s rate limit having been exhausted for the resource.
* 500 INTERNAL SERVER ERROR: Something is horribly wrong.
* 502 BAD GATEWAY: The service is down or being upgraded. Try again later.
* 503 SERVICE UNAVAILABLE: The service is up, but overloaded with requests. Try again later.
* 504 GATEWAY TIMEOUT: Servers are up, but the request couldn’t be serviced due to some failure within our stack. Try again later.

### HTTP GET
* 200 OK: The request was successful and the response body contains the representation requested.
* 302 FOUND: A common redirect response; you can GET the representation at the URI in the Location response header.
* 304 NOT MODIFIED: There is no new data to return.

### HTTP POST or PUT
* 201 OK: The request was successful, we updated the resource and the response body contains the representation.
* 202 ACCEPTED: The request has been accepted for further processing, which will be completed sometime later.

### HTTP DELETE
* 202 ACCEPTED: The request has been accepted for further processing, which will be completed sometime later.
* 204 OK: The request was successful; the resource was deleted.
