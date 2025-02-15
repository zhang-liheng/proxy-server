# Web proxy

This is a proxy server that can handle http requests and cache objects.

Every single connection is handled by a thread, which reads a request line, determine if it is a request, and direct the `doit` routine to handle the rest. The `doit` routine will read request headers and search the cache for a previous response from the server.

- If a cached response is found, the routine will directly forward it to the client.
- Otherwise it will send the client's request to the web server, read the response from web server, forward it to the client, and store it in the cache.

Read `proxy.c` for more details.