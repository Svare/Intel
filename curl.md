# CURL

`Options`
```
-s : Avoid showing progress bar
-D - : Dump headers to a file, but - sends it to stdout
-o /dev/null : Ignore response body

This is better than -I as it doesn't send a HEAD request, which can produce different results.
It's better than -v because you don't need so many hacks to un-verbose it

--cookie 'key=value'
```