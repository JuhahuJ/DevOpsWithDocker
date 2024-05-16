FROM golang:alpine as build

WORKDIR /usr/src/app

COPY /example-backend ./

ENV REQUEST_ORIGIN=http://localhost:5000

RUN  go get -d -v && go build && adduser -D appuser


FROM scratch

EXPOSE 8080

WORKDIR /usr/src/app

COPY --from=build /usr/src/app/server /usr/src/app/server
COPY --from=build /etc/passwd /etc/passwd

USER appuser

CMD ["./server"]
