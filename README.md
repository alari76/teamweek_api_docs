TeamWeek API v2
===============

##Introduction##
The API accepts only JSON requests. Please make sure you're setting Content-type: application/json in your request header or append .json to every URI. Each request returns a JSON-encoded body. 

The result of each action is communicated via standard HTTP response codes.

##Basics##
The API is accessible at https://teamweek.com/api/v2/

Main objects in the API have a 'template', accessible under (with GET) https://teamweek.com/api/v2/:account_id/:object/new.json
eg: for projects use https://teamweek.com/api/v2/:account_id/projects/new.json
the response is:
```json
{
	"project":
		{
			"name":"text",
			"client_id":"integer",
			"color":"string",
			"active":"boolean"
		},
	"links":[
		{
			"href":"https://teamweek.com/api/v2/:account_id/projects",
			"rel":"create",
			"method":"POST"
		},
		{
			"href":"https://teamweek.com/api/v2/:account_id/projects/:id",
			"rel":"update",
			"method":"PUT"
		}, 
		{
			"href":"https://teamweek.com/api/v2/:account_id/projects/:id",
			"rel":"read",
			"method":"GET"
		},
		{
			"href":"https://teamweek.com/api/v2/:account_id/projects/:id",
			"rel":"delete",
			"method":"DELETE"
		},
		{
			"href":"https://teamweek.com/api/v2/:account_id/projects",
			"rel":"list",
			"method":"GET"
		}
	]
}
```
This basically means that a projects has the fields of name, client_id, color and active and with types text, integer, string and boolean (text and string are basically the same, difference is between length) 
Also, the links part - href is the URL you can use for an action, rel shows the action, method shows the HTTP method, eg: to create a project use the URL https://teamweek.com/api/v2/:account_id/projects and POST the fields and you're done.

Required fields will be added to the 'template' in near future.

For update you do not need to send all the fields, just the changed ones.

##API token##

Each user in TeamWeek.com has an API token. They can find it under "My Profile" in their TeamWeek account.

##Authentication##

To use the API, you need to authenticate yourself. This can be done via token.

If authentication fails, HTTP status code 403 is returned. You can read more about authentication and see sample requests [here](chapters/authentication.md).

##Help us towards a better API##

The TeamWeek API has moved to Github so you could actively participate in helping us making the API better. If you have any requests or you found a bug, you can use Github issues to let us know. You can also fork the docs and send a pull request with improvements
