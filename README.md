# Todo App

This is a test app for building a web API using ASP.NET Core.

Based on [this tutorial](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-web-api?view=aspnetcore-6.0&tabs=visual-studio-code).

## To Run

```bash
dotnet run
```

The service will then run on: https://localhost:7103/

## To See All Todo Items

```bash
http --verify no https://localhost:7103/api/todoitems | jq '.'
```

```json
[]
```

## To Create A Todo Items

```bash
http --verify no https://localhost:7103/api/todoitems name="This thing I need to do" | jq '.'
```

```json
{
    "id": 1,
    "isComplete": false,
    "name": "This thing I need to do"
}
```

## To Update A Todo Item

You have to supply _all_ fields, not just the ones that changed.

```bash
http --verify no PUT https://localhost:7103/api/todoitems/1 id:=1 name="ASP.NET Core web API" isComplete:=false
```

A `PUT` request only returns a `204` status code.  Use a `GET` request to fetch
the latest state of the todo item.

## To Delete A Todo Item

```bash
http --verify no DELETE https://localhost:7103/api/todoitems/1
```

A `DELETE` request only returns a `204` status code.
