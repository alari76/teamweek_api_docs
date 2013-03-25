To-dos
==========

##Get todos for a task list##

To-dos are part of tasks list, but one can also query all to-dos for a task

`GET https://teamweek.com/api/v2/:account_id/tasks/:task_id/todos.json`

Returns all to-dos for task, example:

```json
[
  {
    "done":true,
    "id":1234567,
    "name":"Todo #1",
    "weight":0,
    "account_version":7909
  },
  {
    "done":true,
    "id":1234567,
    "name":"Todo #2",
    "weight":1,
    "account_version":7909
  }
]
```

##Template for fields##

`GET https://teamweek.com/api/v2/:account_id/tasks/:task_id/todos/new.json`

```json
{
  "todo":{
    "task_id":"integer",
    "name":"text",
    "done":"boolean",
    "weight":"integer"
  },
  ....
}
```

##Create to-do##

`POST https://teamweek.com/api/v2/:account_id/tasks/:task_id/todos.json`

Use the fields from template as properties. A successful create returns the newly created object:

```json
{
  "done":true,
  "id":1234567,
  "name":"Todo #3",
  "weight":1,
  "account_version":7909
}
```

##Update to-do##

`PUT https://teamweek.com/api/v2/:account_id/tasks/:task_id/todos/:todo_id.json`

Use the fields from template as properties. A successful update returns the newly updated object:

```json
{
  "done":true,
  "id":1234567,
  "name":"Todo #3",
  "weight":1,
  "account_version":7909
}
```

##Delete to-do##

`DELETE https://teamweek.com/api/v2/:account_id/tasks/:task_id/todos/:todo_id.json`
