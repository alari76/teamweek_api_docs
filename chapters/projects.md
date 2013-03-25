Projects
==========

##Get projects list##
`GET https://teamweek.com/api/v2/:account_id/projects.json`

Returns all active projects, example:

```json
[
  {
    "active":true,
    "client_id":null,
    "color":"#bd8528",
    "id":1234567,
    "name":"Project name",
    "undone_tasks":7,
    "undone_estimate":0,
    "integration_accounts":[
      {"integration_name":"toggl"}
    ],
    "background_class":"yellow",
    "client_name":"",
    "account_version":"8881"
  },
  {
    "active":true,
    "client_id":null,
    "color":"#e67399",
    "id":1234567,
    "name":"Project #2",
    "undone_tasks":0,
    "undone_estimate":0,
    "integration_accounts":[],
    "background_class":"purple",
    "client_name":"",
    "account_version":"8881"
  }
]
```

To get a list of archived projects include the filter parameter with the value archived, example:

`GET https://teamweek.com/api/v2/:account_id/projects.json?filter=archived`

To get both active and archived projects, use filter=all

`GET https://teamweek.com/api/v2/:account_id/projects.json?filter=all`

##Get project##

`GET https://teamweek.com/api/v2/:account_id/:project_id.json`

```json
{
  "active":true,
  "client_id":null,
  "color":"#bd8528",
  "id":1234567,
  "name":"Project name",
  "undone_tasks":7,
  "undone_estimate":0,
  "integration_accounts":[
    {"integration_name":"toggl"}
  ],
  "background_class":"yellow",
  "client_name":"",
  "account_version":"8881"
}
```

##Template for fields##

`GET https://teamweek.com/api/v2/:account_id/projects/new.json`

```json
{
  "project":
    {
      "name":"text",
      "client_id":"integer",
      "color":"string",
      "active":"boolean"
    }
  ....
}
```

##Create project##

`POST https://teamweek.com/api/v2/:account_id/projects.json`

Use the fields from template as properties. A successful create returns the newly created object:

```json
{
  "active":true,
  "client_id":null,
  "color":"#bd8528",
  "id":1234567,
  "name":"Project name",
  "undone_tasks":7,
  "undone_estimate":0,
  "integration_accounts":[
    {"integration_name":"toggl"}
  ],
  "background_class":"yellow",
  "client_name":"",
  "account_version":"8881"
}
```

##Update project##

`PUT https://teamweek.com/api/v2/:account_id/:project_id.json`

Use the fields from template as properties. A successful update returns the newly created object:

```json
{
  "active":true,
  "client_id":null,
  "color":"#bd8528",
  "id":1234567,
  "name":"Project name",
  "undone_tasks":7,
  "undone_estimate":0,
  "integration_accounts":[
    {"integration_name":"toggl"}
  ],
  "background_class":"yellow",
  "client_name":"",
  "account_version":"8881"
}
```

##Delete project##

`DELETE https://teamweek.com/api/v2/:account_id/:project_id.json`