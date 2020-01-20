## Test task

| goroutines |
|---|
| Turn-in directory: goroutines/ |
| Files to turn in: main.go, *.go |
| Allowed function: all standard library |
The program reads from stdin, the contents of the URL. You must send an HTTP request to each URL using the GET method and count the number of Go entries in the response body. At the end of the work, the application displays the total number of "Go" lines found in all URLs passed, for example:
```
$> cat urls | go run src/cmd/wb-test/main.go
Count for https://golang.org/: 9
Count for https://golang.org/doc/: 64
Count for https://golang.org/compress/: 6
...
...
Total: 253
```
Each URL should begin processing immediately after reading and in parallel with the other. URLs must be processed in parallel, but no more than k = 5 at a time. URL handlers should not create unnecessary goroutines, ex.: if k = 5, and only 2 URL's are processed, there should't be 5 goroutines.

To test the program, use the following file `urls`:
```
https://golang.org/
https://golang.org/doc/
https://golang.org/pkg/compress/
https://golang.org/pkg/compress/gzip/
https://golang.org/pkg/crypto/md5/
https://golang.org/pkg/debug/pe/
https://golang.org/pkg/log/syslog/
https://golang.org/pkg/sort/
https://golang.org/pkg/strconv/
https://golang.org/pkg/strings/
https://golang.org/pkg/sync/
https://golang.org/pkg/strings/
https://golang.org/pkg/time/
https://golang.org/pkg/unicode/
https://golang.org/pkg/unsafe/
https://godoc.org/golang.org/x/benchmarks
https://godoc.org/golang.org/x/net
https://godoc.org/golang.org/x/mobile
```