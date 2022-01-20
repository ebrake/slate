# Errors

The Platform API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Unauthorized -- Your API key is wrong.
404 | Not Found -- The specified iteam could not be found.
405 | Method Not Allowed -- You tried to access an API with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json or multipart as required.
410 | Gone -- The API requested has been removed from our servers.
429 | Too Many Requests -- You're requesting too many items! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
