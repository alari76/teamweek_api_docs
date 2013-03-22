Authentication
==========

To use the API, you need to authenticate yourself. This can be done via API token. The token can be found on a users profile page.

To authenticate just include the token in your request.

If authentication fails, HTTP status code 403 is returned.

##Example of an authenticated request##

The following request creates a client named TestClient under account with an id of '1234567'

```shell
curl -X POST -d "auth_token=<api token>&name=TestClient" https://teamweek.com/api/v2/1234567/clients.json
```
Successful response

```json
{
	"active":true,
	"id":1234567,
	"name":"TestClient",
	"integration_accounts":[],
	"projects_count":0,
	"account_version":1234567
}
```
Failure
```json
{
	"errors":
		{
			"name":["has already been taken"]
		},
	"account_version":1234567
	}
```