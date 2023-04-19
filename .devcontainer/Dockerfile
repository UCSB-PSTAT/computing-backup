FROM alpine:latest
RUN apk update
RUN apk add curl go gcc git bash musl-dev openssl-dev ca-certificates && update-ca-certificates

# Golang install
RUN curl -OL https://go.dev/dl/go1.20.3.src.tar.gz
RUN tar -C /usr/local -xzf go1.20.3.src.tar.gz
RUN cd /usr/local/go/src && ./make.bash
ENV PATH=$PATH:/usr/local/go/bin
RUN rm go1.20.3.src.tar.gz
RUN apk del go
RUN go version

# NPM + nodejs
RUN apk add --update nodejs npm

# claat
RUN go install github.com/googlecodelabs/tools/claat@latest

