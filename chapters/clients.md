Clients
==========

##Get clients list##
`GET https://teamweek.com/api/v2/:account_id/clients.json`

Returns all active clients, example:

```json
[
  {
    "active":true,
    "id":1234567,
    "name":"Client #1",
    "integration_accounts":[
      {"integration_name":"toggl"}
    ],
    "projects_count":0,
    "account_version":8881
  },
  {
    "active":true,
    "id":1234567,
    "name":"Client #2",
    "integration_accounts":[
      {"integration_name":"toggl"}
    ],
    "projects_count":5,
    "account_version":8881
  }
]
```

To get a list of archived clients include the filter parameter with the value archived, example:

`GET https://teamweek.com/api/v2/:account_id/clients.json?filter=archived`

To get both active and archived clients, use filter=all

`GET https://teamweek.com/api/v2/:account_id/clients.json?filter=all`

##Get client##

`GET https://teamweek.com/api/v2/:account_id/:client_id.json`

```json
{
  "active":true,
  "id":1234567,
  "name":"Client #1",
  "integration_accounts":[
    {"integration_name":"toggl"}
  ],
  "projects_count":0,
  "account_version":8881
}
```

##Template for fields##

`GET https://teamweek.com/api/v2/:account_id/clients/new.json`

```json
{
  "project":
    {
      "name":"text",
      "active":"boolean"
    }
  ....
}
```

##Create client##

`POST https://teamweek.com/api/v2/:account_id/clients.json`

Use the fields from template as properties. A successful create returns the newly created object:

```json
{
  "active":true,
  "id":1234567,
  "name":"Client #1",
  "integration_accounts":[],
  "projects_count":0,
  "account_version":8881
}
```

##Update client##

`PUT https://teamweek.com/api/v2/:account_id/:client_id.json`

Use the fields from template as properties. A successful update returns the newly updated object:

```json
{
  "active":true,
  "id":1234567,
  "name":"Client #1",
  "integration_accounts":[
    {"integration_name":"toggl"}
  ],
  "projects_count":0,
  "account_version":8881
}
```

##Delete client##

`DELETE https://teamweek.com/api/v2/:account_id/:client_id.json`