TeamWeek API v2
===============

##Introduction##
The API accepts only JSON requests. Please make sure you're setting Content-type: application/json in your request header or append .json to every URI. Each request returns a JSON-encoded body. 

The result of each action is communicated via standard HTTP response codes.

##API token##

Each user in TeamWeek.com has an API token. They can find it under "My Profile" in their TeamWeek account.

##Authentication##

To use the API, you need to authenticate yourself. This can be done via token.

If authentication fails, HTTP status code 403 is returned. You can read more about authentication and see sample requests [here](chapters/authentication.md).

##Help us towards a better API##

The TeamWeek API has moved to Github so you could actively participate in helping us making the API better. If you have any requests or you found a bug, you can use Github issues to let us know. You can also fork the docs and send a pull request with improvements
