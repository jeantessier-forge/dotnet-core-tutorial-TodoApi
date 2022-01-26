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
