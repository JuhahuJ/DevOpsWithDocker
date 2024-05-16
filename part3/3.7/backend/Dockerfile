FROM golang:alpine

EXPOSE 8080

WORKDIR /usr/src/app

COPY /example-backend ./

ENV REQUEST_ORIGIN=http://localhost:5000

RUN apk add --no-cache ca-certificates && go build && adduser -D appuser

USER appuser

CMD ./server
