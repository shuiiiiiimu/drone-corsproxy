# drone-corsproxy

**checkout from https://github.com/mattbailey/docker-corsproxy**

## Usage

Environment variables:

```
PROXY_HOST      Required: host to proxy requests to (e.g. https://www.google.com)
EXPOSE_HEADERS  Optional: response headers on the proxy host you want exposed to the client browser (comma separated)
ALLOW_HEADERS   Optional: request headers from the client browser you want exposed to the proxy host (comma separated)
API_RECTIFY     Optional: form: 'foo|bar', would proxy /foo and /bar to /foo/ and /bar/, this is to fix poorly planned APIs
```

Example:

```
docker run --rm -t \
  -e PROXY_HOST=https://www.google.com \
  -e ALLOW_HEADERS=X-MyCustom-API-Key,X-Some-Token \
  -e EXPOSE_HEADERS=X-Some-Response-Token \
  -e API_RECTIFY='foo|bar' \
  -p 8080:80 \
  mattbailey/docker-corsproxy
```
