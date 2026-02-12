HttpContext is a class in ASP.NET. Every time a new request comes into ASP.NET, a new HttpContext object is created that has all the information in the request such as:
- The method (`GET`, `POST`, `PUT`)
- Request information such as headers, the URL, form data, the query string
- The response status code
- Information about the authenticated user, session, etc.

This is really important and valuable information! So HttpContext is a frequently accessed class.

## Accessing HttpContext Information
