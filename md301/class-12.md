# CRUD

- 100’s = header part of the request has been received and the server will try to comply with a transmission demand of the client

- 200’s = success codes. request was accepted. ((202), this only that it met all validation requirements at the time of sending).

- 300’s = resource they are requesting isn’t available (check the new location).

- 400’s = the client error codes. They are all about invalid requests a client sent to a server.

- 500’s = overwhelmed servers or unreachable servers behind proxies, its like try again later..

- What is a status code 202? OK

- What is a status code 308?

     Permanent Redirect - This tells the client to use another URL to access the resource and not use the current URL anymore.

- What code would you use if an update didn’t return data to a client? 204 No Content

- What code would you use if a resource used to exist but no longer does? 204 No Content

- What is the ‘Forbidden’ status code?

     403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.
