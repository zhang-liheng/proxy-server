# Web proxy

This is a proxy that can deal with GET method and caches objects.

Every single connection is handled by a thread, which reads a request line, determine if it is a GET request, and direct doit routine (refer to tiny web server) to handle the rest. The doit routine reads request headers, search the cache for fit, send client request to web server, read response from web server, forward it to client, and store it in the cache.