# Dockerfiles

My personal collection of Dockerfiles.

## Tricks Library

### ctop

```
docker run --rm -it \
  --name=ctop \
  -v /var/run/docker.sock:/var/run/docker.sock \
  quay.io/vektorlab/ctop:latest
```
