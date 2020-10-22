# go-mbtiles-server

Go HTTP server for serving MBTiles databases.

## Tools

```
$> make cli
go build -mod vendor -o bin/server cmd/server/main.go
```

### server

```
$> ./bin/server -h
  -server-uri string
    	A valid aaronland/go-http-server URI string. (default "http://localhost:8080")
  -tiles-extension string
    	The extension (minus the leading dot) for your MBTiles databases. (default ".mbtiles")
  -tiles-path string
    	The relative path to serve tiles from. (default "/tiles/")
  -tiles-pattern string
    	A valid Go language regular expression for validating requests. The pattern needs to return five values: name of the MBTiles file, Z, X and Y tile values and a file extension used to determine content type. (default "/tiles/([a-z-]+)/(\\d+)/(\\d+)/(\\d+)\\.([a-z]+)$")
  -tiles-source string
    	Path to the directory containing your MBTiles databases.
```	

For example:

```
$> ./bin/server -tiles-source /usr/local/mbtiles/
2020/10/21 21:53:00 Listening on http://localhost:8080
```

#### Lambda

_Please write me._

## See also

* https://github.com/aaronland/go-http-mbtiles
* https://github.com/aaronland/go-http-server