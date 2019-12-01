# webapi

## Editor

Install mono https://www.mono-project.com/download/stable/. Thisis required for the vim plugin. In your `.vimrc`, add:

```
Plugin 'OmniSharp/omnisharp-vim'
```
## Installation 

```bash
$ dotnet new webapi -o aspdotnetcoreapi
$ dotnet dev-certs https --trust
$ dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL
$ dotnet add package Microsoft.EntityFrameworkCore.InMemory
```

## View

```
$ open http://localhost:5001
```

## Scaffold a controller

```bash
$ dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
$ dotnet add package Microsoft.EntityFrameworkCore.Design
# Required to scaffold controller even if you are using PostgreSQL.
$ dotnet add package Microsoft.EntityFrameworkCore.SqlServer
$ dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL.Design
$ dotnet tool install --global dotnet-aspnet-codegenerator
$ dotnet aspnet-codegenerator controller -name TodoItemsController -async -api -m TodoItem -dc TodoContext -outDir Controllers
```

## Start

```bash
$ dotnet watch run
```

## API

Create:
```
$ curl -H 'Content-Type: application/json' -X POST -d '{"name": "walk dog", "isComplete": true}' https://localhost:5001/api/TodoItems
```

Get:

```
$ curl https://localhost:5001/api/TodoItems
```

Output:
```
[{"id":1,"name":"walk dog","isComplete":true},{"id":2,"name":"walk dog","isComplete":true}]
```
