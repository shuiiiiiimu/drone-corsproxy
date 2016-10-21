# drone-corsproxy

**checkout from https://github.com/mattbailey/docker-corsproxy**

## Usage

Environment variables:

```
PROXY_HOST      Required: host to proxy requests to (e.g. https://www.google.com)
```

Example:

```
docker run --rm -t \
  -e PROXY_HOST=http://192.168.3.240:8000 \
  -p 8000:80 \
  zhangsm/drone-corsproxy
```
