Tasks
==========

##Get tasks list##
`GET https://teamweek.com/api/v2/:account_id/tasks.json`

Returns all tasks, example:

```json
[
  {
    "backlog":false,
    "color":"#59bfb3",
    "comment":"Task comment",
    "done":false,
    "end_date":null,
    "estimated_hours":null,
    "id":1234567,
    "project_id":1234567,
    "start_date":null,
    "start_time":null,
    "sticky":false,
    "user_id":null,
    "x":20.0,
    "y":19.0,
    "account_version":8881,
    "todos":[
      {
        "done":false,
        "id":1234567,
        "name":"An undone to-do",
        "weight":0
      },
      {
        "done":true,
        "id":1234567,
        "name":"A done to-to",
        "weight":1
      }
    ],
    "project":{
      "id":1234567,
      "name":"A project Name"
    },
    "integration_accounts":[
      {"integration_name":"bcx"}
    ]
  },
  {
    "backlog":false,
    "color":"#59bfb3",
    "comment":"Task comment",
    "done":false,
    "end_date":null,
    "estimated_hours":null,
    "id":1234567,
    "project_id":1234567,
    "start_date":null,
    "start_time":null,
    "sticky":false,
    "user_id":null,
    "x":20.0,
    "y":19.0,
    "account_version":8881,
    "todos":[
      {
        "done":false,
        "id":1234567,
        "name":"An undone to-do",
        "weight":0
      },
      {
        "done":true,
        "id":1234567,
        "name":"A done to-to",
        "weight":1
      }
    ],
    "project":{
      "id":1234567,
      "name":"A project Name"
    },
    "integration_accounts":[
      {"integration_name":"bcx"}
    ]
  }
]
```

Specifing a date range:

`GET https://teamweek.com/api/v2/:account_id/tasks.json?range_start=2012-09-26&days=7`

This returns a weeks tasks starting from 26th of September 2012.

##Get task##

`GET https://teamweek.com/api/v2/:account_id/tasks/:task_id.json`

```json
{
  "backlog":false,
  "color":"#59bfb3",
  "comment":"Task comment",
  "done":false,
  "end_date":null,
  "estimated_hours":null,
  "id":1234567,
  "project_id":1234567,
  "start_date":null,
  "start_time":null,
  "sticky":false,
  "user_id":null,
  "x":20.0,
  "y":19.0,
  "account_version":8881,
  "todos":[
    {
      "done":false,
      "id":1234567,
      "name":"An undone to-do",
      "weight":0
    },
    {
      "done":true,
      "id":1234567,
      "name":"A done to-to",
      "weight":1
    }
  ],
  "project":{
    "id":1234567,
    "name":"A project Name"
  },
  "integration_accounts":[
    {"integration_name":"bcx"}
  ]
}
```

##Template for fields##

`GET https://teamweek.com/api/v2/:account_id/tasks/new.json`

```json
{
  "task":
    {
      "start_date":"date",
      "end_date":"date",
      "project_id":"integer",
      "comment":"text",
      "color":"string",
      "user_id":"integer",
      "x":"float",
      "y":"float",
      "client_id":"integer",
      "sticky":"boolean",
      "done":"boolean",
      "estimated_hours":"decimal",
      "backlog":"boolean",
      "start_time":"time"
    }
  ....
}
```

##Create task##

`POST https://teamweek.com/api/v2/:account_id/tasks.json`

Use the fields from template as properties. A successful create returns the newly created object:

```json
{
  "backlog":false,
  "color":"#59bfb3",
  "comment":"Task comment",
  "done":false,
  "end_date":"2013-03-25",
  "estimated_hours":null,
  "id":1234567,
  "project_id":1234567,
  "start_date":"2013-03-21",
  "start_time":null,
  "sticky":false,
  "user_id":1234567,
  "x":20.0,
  "y":19.0,
  "account_version":8881,
  "todos":[],
  "project":null,
  "integration_accounts":[]
}
```

##Update client##

`PUT https://teamweek.com/api/v2/:account_id/tasks/:task_id.json`

Use the fields from template as properties. A successful update returns the newly updated object:

```json
{
  "backlog":false,
  "color":"#59bfb3",
  "comment":"Task comment",
  "done":true,
  "end_date":"2013-03-25",
  "estimated_hours":null,
  "id":1234567,
  "project_id":1234567,
  "start_date":"2013-03-21",
  "start_time":null,
  "sticky":false,
  "user_id":1234567,
  "x":20.0,
  "y":19.0,
  "account_version":8881,
  "todos":[],
  "project":null,
  "integration_accounts":[]
}
```

##Delete task##

`DELETE https://teamweek.com/api/v2/:account_id/tasks/:task_id.json`

##Search tasks""
`GET https://teamweek.com/api/v2/:account_id/tasks/search?term=foobar`

Where foobar is the term you want to search for. Query matches task description, the project (if task is connected to a project) name and client (if project is connected to a client) name. Term is mached with OR and from the whole (basically a SQL query with LIKE %foobar% is made).
Note: search is case insensitive, so Foobar, foobar, fooBAR all give same results.