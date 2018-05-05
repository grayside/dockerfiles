FROM alpine:3.7

LABEL maintainer="Adam Ross <grayside+dockerfiles@gmail.com>" \
      usage="docker run --rm -v $PWD:/fs grayside/tree" \
      help="docker run --rm grayside/tree --help"

RUN apk --no-cache add tree

ENTRYPOINT ["/usr/bin/tree"]

WORKDIR /fs
