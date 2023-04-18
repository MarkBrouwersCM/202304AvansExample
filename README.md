# Avans - Code example
After cloning this repository, go to the Avans.Demo folder with your favorite
command prompt.

Run the following commands, assuming you have .NET 7.0 SDK installed.

```dotnet run```

```dotnet build --no-restore```

```dotnet run --project Avans.Demo.Web.Api --no-build```

[Open in your browser](http://localhost:5020/swagger/index.html)


**Note**: This demo project will create a SQLite database called avansDemo.db in your Local Application Data folder.

## Testing
Assuming you are still inside the Avans.Demo folder, run the following command

```dotnet test```


## Sample cURL's

### Loading all books
```
curl -X 'GET' \
  'http://localhost:5020/v1.0/books' \
  -H 'accept: text/plain'
```

### Adding a book
```
curl -X 'POST' \
  'http://localhost:5020/v1.0/books' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -d '{
    "isbn": "9781484242216",
    "title": "Rethinking Productivity in Software Engineering",
    "author": "Caitlin Sadowski, Thomas Zimmermann",
    "pages": 310,
    "website": "https://doi.org/10.1007/978-1-4842-4221-6"
  }'
```

### Delete a book
```
curl -X 'DELETE' \
  'https://localhost:5020/v1.0/books/9781484242216' \
  -H 'accept: */*'
```