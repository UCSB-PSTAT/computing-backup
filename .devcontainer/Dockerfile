FROM alpine:latest
RUN apk update
RUN apk add --no-cache curl git make bash musl-dev go openssh openssl-dev ca-certificates python3 && update-ca-certificates

# Golang install
ENV GOROOT /usr/lib/go
ENV GOPATH /go
ENV PATH /go/bin:$PATH
RUN mkdir -p ${GOPATH}/src ${GOPATH}/bin
RUN go version

# NPM + nodejs
RUN apk add --update --no-cache nodejs npm

# claat
RUN go install github.com/googlecodelabs/tools/claat@latest
