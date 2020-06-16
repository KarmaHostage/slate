# Errors

The Karmahostage API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- You don't have access to the key or secret 
404 | Not Found -- The specified secret or key could not be found
405 | Method Not Allowed -- You tried to access the API with an invalid method.
418 | I'm a teapot.
429 | Too Many Requests -- You're making too many requests! Slow down - or upgrade your plan!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
